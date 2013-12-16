MenuDrawerLibrary
=================

Library for implementing sliding menu drawer 

##How to use library :

- This can be either 
     used as a library project (project properties->Android->add Library) 
  or 
     add MenuDrawerLibrary.jar file from MenuDrawerLibrary->bin to libs folder in your project


##How to use

  In your activity add following code
  
    //Initializing drawer with its type and position
    MenuDrawer mMenuDrawer = MenuDrawer.attach(this, MenuDrawer.MENU_DRAG_WINDOW,Position.RIGHT);
    
    //Layout of the page on which you have to add drawer
    mMenuDrawer.setContentView(R.layout.page_layout);
		
	//Layout of the drawer contents
	mMenuDrawer.setMenuView(R.layout.drawer_layout);
	
	//Setting listener for drawer actions
	mMenuDrawer.setOnDrawerStateChangeListener(new OnDrawerStateChangeListener() {

	  @Override
	  public void onDrawerStateChange(int oldState, int newState) {
		  if (newState == MenuDrawer.STATE_CLOSED) {
			  // do something ...
	  	} else if (newState == MenuDrawer.STATE_OPENING || newState == MenuDrawer.STATE_DRAGGING
				|| newState == MenuDrawer.STATE_OPEN) {
			  // do something ...
 		  }
	  }
    });
	  
    //Opening menu drawer on button click
    mMenuDrawer.openMenu();
    
    //Closing menu drawer
    mMenuDrawer.closeMenu();
