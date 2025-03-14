What sort of documents and code snippets I should have in this?


# Understanding Qlik for Angular Developers
High Level overview explaining :
- how qlik works
- what's so special about it
- Different types of qlik servers, qlik cloud vs qap servers, and how they're different & what benefits each one provide

    - modify it to explain Qlik Cloud vs QAP servers
    - Talk a lot more about selections and how they work


PROMPTS?
For the following How to guides, always defer to using qlik-api-ts, and always output .md compatible content, always include a basic javascript and angular 19 version of code snippets, with the ultimate aim of generating a web app that connects to a qlik app in order to display and drive embedded and custom d3.js charts in the web app.

Authorising & Authenticating
- How do do this with Qlik from a web app using qlik-api-ts
 library for the following qlik server types:
    - Qlik SaaS
    - QAP servers

Managing connections to Qlik Servers and Qlik Apps
- How you open connections to a tenancy, then from that how to connect to specific apps
- Write about limitations and whether it's possible to manage multiple connections at the same time

Qlik Embedding
- High level how embedding of charts and objects work
- What are the limitations and write about how a lot of the work falls onto the qlik developer
- How you can use the qlik-embed framework in a web app
- List the limitations of what can be embedded, make sure it's clear that third party Qlik charts developed by companies like VizLib are not embeddable, also that it wasn't made to work with SSR web apps.

Qlik Elements:
- Qlik Sheets
    - Brief description of qlik Sheets, and what you can do with them using qlik-api-ts
    - Put a caveat about how qlik sheets are useful for when you want to embed the whole sheet, but for highly customisable dashboards, using specific qlik objects better.

- Qlik Objects
    - What they are
    - Briefly speak about how there are 2 options, you can generate charts on the fly programatically or you can connect to existing ones within a qlik app
    - How to find it's unique objectId
    - How you can connect to a specific qlik object, and why it's important to add an on change event listener
    - Once you've opened the connection, how do you get the data out of it, start with the highlevel steps of connecting using the object Id, getting the layout and the relevant details from their in order to get all the relevant content out of the hypercube etc.
    - Go into detail on how to get data from the following object types:
        - tables
            - focus on the concept that most data used by mashup developer using d3.js will be in a table format
            - list the gotcha's especially when it comes to dynamic tables that show and hide columns based on changes in selections.
            - Explain the difference between a pivot table and a straight table.
        - filter panes and listboxes
            - specifically delineate between the 2 and discuss why getting options from a filter pane isn't as efficient as connecting to the listbox directly. 
            - Get into some more detail on the different states involved in a listbox and how that looks in the json object returned
            - Explain that listboxes are generally based off a field, but that they can also be based off a calculation.
            - Explain what happens when a selection is made, and how this can affect other objects especially listboxes; reiterate why the onchange event listener was added
        - fields
            - what they are
            - when would you use them vs a listbox
            - how to connect to them and change selections
        - variables
            - what they are
            - what you'd use them for
            - how to connect to them and get the value out
            - how to change the value       
