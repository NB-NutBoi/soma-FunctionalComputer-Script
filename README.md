# Features:

Basic desktop system:<br /> - Support for different file icons<br /> - Support for different wallpapers<br />

---------------------------------------

Extremely basic windowing (TODO):<br /> - Multiple application windows<br />

---------------------------------------

Somewhat flexible application API (TODO example)

---------------------------------------
# How to make a computer
DISCLAIMER: Don't expect this to work perfectly, it's just an experiment and it does not save the current state of the computers on load (thanks hpl).<br /><br />

---------------------------------------

Basic setup on a map script:

```as


#include /*insert custom computer script here*/



//...

ComputerData data(cVector2f(520,525),"background1","cursor_test",cVector2f(0.63f,1));
		
FunctionalComputer computer(data);



//Setup

void Setup()
{
  /*will add a file 
  (these do save for the sake of having a consistent desktop, but the icons break on load unless they're reset every time the map loads )
  (feel free to make the files array volatile for this reason)*/
  computer.AddFile(ComputerFile(cVector2f(0,0),"test","file",TextReader("test - Text reader",AppTextContent("TEST"))));
}




//Gui functions per terminal

void Computer_OnGui(const tString&in asEntityName, float afTimeStep)
{
  computer.DrawComputer(afTimeStep);
}

void Computer_GuiEnter(const tString&in asEntityName)
{
  computer.updateTrackMouse(true);
}

void Computer_GuiLeave(const tString&in asEntityName)
{
  computer.updateTrackMouse(false);
}

```
