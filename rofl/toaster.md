---
layout: page
title: The Tale of the Toaster
---

Once upon a time, in a kingdom not far from here, a king summoned 
two of his advisors for a test. He showed them both a shiny metal box with two 
slots in the top, a control knob, and a lever. "What do you think this 
is?"

One advisor, an engineer, answered first. "It is a toaster," 
he said.

The king asked, "How would you design an embedded computer 
for it?"

The engineer replied, "Using a four-bit microcontroller, 
I would write a simple program that reads the darkness knob and quantizes its 
position to one of 16 shades of darkness, from snow white to coal black. The 
program would use that darkness level as the index to a 16-element table of 
initial timer values. Then it would turn on the heating elements and start the 
timer with the initial value selected from the table. At the end of the time 
delay, it would turn off the heat and pop up the toast. Come back next week, 
and I'll show you a working prototype." 

The second advisor, a computer scientist, immediately recognized 
the danger of such shortsighted thinking. He said, "Toasters don't just 
turn bread into toast, they are also used to warm frozen waffles. What you see 
before you is really a breakfast food cooker. As the subjects of your kingdom 
become more sophisticated, they will demand more capabilities. They will need 
a breakfast food cooker that can also cook sausage, fry bacon, and make scrambled 
eggs. A toaster that only makes toast will soon be obsolete. If we don't look 
to the future, we will have to completely redesign the toaster in just a few 
years."

"With this in mind, we can formulate a more intelligent 
solution to the problem. First, create a class of breakfast foods. Specialize 
this class into subclasses: grains, pork, and poultry. The specialization process 
should be repeated with grains divided into toast, muffins, pancakes, and waffles; 
pork divided into sausage, links, and bacon; and poultry divided into scrambled 
eggs, hard-boiled eggs, poached eggs, fried eggs, and various omelet classes."

 "The ham and cheese omelet class is worth special attention 
because it must inherit characteristics from the pork, dairy, and poultry classes. 
Thus, we see that the problem cannot be properly solved without multiple inheritance. 
At run time, the program must create the proper object and send a message to 
the object that says, 'Cook yourself.' The semantics of this message depend, 
of course, on the kind of object, so they have a different meaning to a piece 
of toast than to scrambled eggs." 

"Reviewing the process so far, we see that the analysis 
phase has revealed that the primary requirement is to cook any kind of breakfast 
food. In the design phase, we have discovered some derived requirements. Specifically, 
we need an object-oriented language with multiple inheritance. Of course, users 
don't want the eggs to get cold while the bacon is frying, so concurrent processing 
is required, too." 

"We must not forget the user interface. The lever that lowers 
the food lacks versatility, and the darkness knob is confusing. Users won't 
buy the product unless it has a user-friendly, graphical interface. When the 
breakfast cooker is plugged in, users should see a cowboy boot on the screen. 
Users click on it, and the message 'Booting Windows NT v. 6.0' appears on the 
screen. (NT 6.0 should be out by the time the product gets to the market.) Users 
can pull down a menu and click on the foods they want to cook."

 "Having made the wise decision of specifying the software 
first in the design phase, all that remains is to pick an adequate hardware 
platform for the implementation phase. An Intel Pentium Pro with 64MB of memory, 
a 3.0GB hard disk, and a 21" monitor should be sufficient. If you select 
a multitasking, object oriented language that supports multiple inheritance 
and has a built-in GUI, writing the program will be a snap. (Imagine the difficulty 
we would have had if we had foolishly allowed a hardware-first design strategy 
to lock us into a four-bit microcontroller!)." 

The king wisely had the computer scientist beheaded, and they 
all lived happily ever after.
