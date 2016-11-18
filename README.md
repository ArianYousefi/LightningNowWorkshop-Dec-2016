# Lightning Now Workshop

##Exercise 4 – Creating a Simple Lightning Component

###Exercise Goals

* Build a simple Hello World component
* Explore basic concepts of Lightning Component markup
* Understand how to use attributes for data binding

###Step 1 - Hello World

1. In the Developer Console, choose **New > Lightning Component**.
2. Give the component a name of **HelloWorld**.
3. Check the option **Lightning Record Page**.
4. Add "Hello World" to the component.
5. Save the file.

###Step 2 - Add the component to a page
1. In the Sales app, click the Accounts tab.
2. Filter the list to show **All Accounts**.
3. Click on **United Oil & Gas Corp**.
4. Choose **Edit Page** from the Setup menu.
5. Locate your HelloWorld component in the Component List.
6. Drag it onto the page and place it at the top of the right-hand column, above the Activity and Chatter tabs.
7. Click the Save button.
8. Click the Activate button.
9. Leave the option set to **Assign this page as the default record page** and click Next.
10. Click Save.
11. Click the Back button in the upper righthand corner of App Builder to return to the account page.

###Step 3 - Understanding Lightning Component basics
1. Replace the "Hello World" text with:

		<aura:attribute name="greeting" type="String" default="World" />
    	Hello, {!v.greeting}!
    	
2. Save and reload the account page.
3. Add the following on a new line:

		<ui:inputText aura:id="userInput" change="{!c.updateGreeting}"></ui:inputText>
		
4. Click the Controller button on the right-hand side of the Dev Console.
5. Replace the Controller's contents with:

		({
			updateGreeting : function(component, event, helper) {
				var newGreeting = component.find("userInput").get("v.value");
				component.set("v.greeting", newGreeting);
			}
		})

6. Save the Controller file and the Component.
7. Refresh the account page.
8. Type your name in the input and press Tab or Return.