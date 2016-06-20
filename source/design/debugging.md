# Debugging and Testing

Debug and test your app thoroughly before launching with real participants. We
recommend going through the following steps:

1. Grab some friends and have them play with your app. Are the instructions
clear? Is it obvious what a participant should do?
2. Test your app using multiple browsers in a local machine. Try dropping out of
your experiment and seeing how your code handles it. Reconnect to your
experiment (within a short amount of time) and ensure that data isn't lost.
3. Use the MTurk Sandbox for end-to-end testing, and make sure that the HIT can
be submitted correctly and is collecting all the data that you need.

Think everything's ready? The ultimate test of your app is to conduct a 
[pilot](../launching/pilot.md). 

## Code Troubleshooting

Because TurkServer runs alongside your app on both the server and client,
strange behavior can occur when writing code without thoughtfulness. While we've
tried our best to prevent easily-avoidable problems, some issues might still
arise due to these reasons. These are some things to be aware of:

- **CSS conflicts**. TurkServer uses regular Bootstrap classes with no modification. If you use CSS classes that conflict with Bootstrap in your app, or selectors for unqualified tags, the admin backend will likely be messed up.
- **Meteor template name conflicts**. TurkServer templates all have the prefix `ts`.
- **Handlebars helper conflicts**. Internal TurkServer global helpers have the prefix `_ts`.
