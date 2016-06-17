# Debugging and Testing

Debug your app thoroughly in local mode before launching on MTurk.
Grab some friends or use multiple browsers. Test things like dropouts, 
reconnections, and so on.

Use the MTurk Sandbox for end-to-end testing.

Think everything's ready? The ultimate test of your app is to conduct a 
[pilot](pilot). 

# Notes and Troubleshooting

Because TurkServer runs alongside your app on both the server and client,
strange behavior can occur when writing code without thoughtfulness. While we've
tried our best to prevent easily-avoidable problems, some issues might still
arise due to these reasons. These are some things to be aware of:

- **CSS conflicts**. TurkServer uses regular Bootstrap classes with no modification. If you use CSS classes that conflict with Bootstrap in your app, or selectors for unqualified tags, the admin backend will likely be messed up.
- **Meteor template name conflicts**. TurkServer templates all have the prefix `ts`.
- **Handlebars helper conflicts**. Internal TurkServer global helpers have the prefix `_ts`.
