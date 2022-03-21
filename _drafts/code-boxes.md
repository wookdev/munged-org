---
layout: post
title: Code Boxes
---

Some awk for your amusement:

```awk
# pass 'id' in via the -v switch on the awk command line
#
/---/ && NR > 1 \
    {
        printf "mtid: %d\n", id
        printf "redirect_from:\n"
        printf "  - /saga/%d.html\n", id
    }
# print all lines
    { print $0 }
```

And its shell script:

```shell
#!/bin/bash

exdir=$(dirname $0)
pfx=$(mktemp -d /tmp/$(basename $0).XXXXXXXXXX) || exit 1

for sourcefile in *.md
do

    # yeah, I could have done this way better, but "cut" is what I could remember
    id=$(echo ${sourcefile} | cut -d '.' -f 1 | cut -d '-' -f 4- | egrep '^[0-9]+' );

    if [ -n "${id}" ]; then
    
        tmpfile=${pfx}/${sourcefile}
        cp ${sourcefile} ${tmpfile}
        
        echo $id $tmpfile $sourcefile

        awk -v id=$id -f ${exdir}/addid.awk $tmpfile > $sourcefile

    fi
done

exit 0
```

Javascript:

```javascript
// ES6 syntax
function Person(){
  this.age = 0;

  setInterval(() => {
    // `this` now refers to the Person object, brilliant!
    this.age++;
  }, 1000);
}

var p = new Person();
```

# Ruby

```ruby
#!/usr/bin/env ruby
# frozen_string_literal: true

STDOUT.sync = true

$LOAD_PATH.unshift File.expand_path("../lib", __dir__)

require "jekyll"
require "mercenary"

Jekyll::PluginManager.require_from_bundler

Jekyll::Deprecator.process(ARGV)

Mercenary.program(:jekyll) do |p|
  p.version Jekyll::VERSION
  p.description "Jekyll is a blog-aware, static site generator in Ruby"
  p.syntax "jekyll <subcommand> [options]"

  p.option "source", "-s", "--source [DIR]", "Source directory (defaults to ./)"
  p.option "destination", "-d", "--destination [DIR]",
    "Destination directory (defaults to ./_site)"
  p.option "safe", "--safe", "Safe mode (defaults to false)"
  p.option "plugins_dir", "-p", "--plugins PLUGINS_DIR1[,PLUGINS_DIR2[,...]]", Array,
    "Plugins directory (defaults to ./_plugins)"
  p.option "layouts_dir", "--layouts DIR", String,
    "Layouts directory (defaults to ./_layouts)"
  p.option "profile", "--profile", "Generate a Liquid rendering profile"

  Jekyll::External.require_if_present(Jekyll::External.blessed_gems) do |g, ver_constraint|
    cmd = g.split("-").last
    p.command(cmd.to_sym) do |c|
      c.syntax cmd
      c.action do
        Jekyll.logger.abort_with "You must install the '#{g}' gem" \
          " version #{ver_constraint} to use the 'jekyll #{cmd}' command."
      end
    end
  end

  Jekyll::Command.subclasses.each { |c| c.init_with_program(p) }

  p.action do |args, _|
    if args.empty?
      Jekyll.logger.error "A subcommand is required."
      puts p
      abort
    else
      subcommand = args.first
      unless p.has_command? subcommand
        Jekyll.logger.abort_with "fatal: 'jekyll #{args.first}' could not" \
          " be found. You may need to install the jekyll-#{args.first} gem" \
          " or a related gem to be able to use this subcommand."
      end
    end
  end
end
```