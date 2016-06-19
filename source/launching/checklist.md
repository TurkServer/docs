# Pre-Launch Checklist

If you've done this before, you know that launching a live app to hundreds of
 people can be unnerving and stressful, because of the potential of things 
 going wrong. The bad news is that stress can cause you to forget things and 
 even more things can go wrong! The good news is that the best way to combat 
 this is by making a checklist—just like NASA does before space shuttle 
 launches.

## Example Checklist

This is a checklist of common things we've done before running experiments. 
You should copy it somewhere and augment it with things that are specific to 
your experiment. 

### General Tasks

- Make sure any [post-experiment cleanup](post-experiment) from your last 
session is all done

- Make sure the code on your deployment server is up to date

- Make sure there is enough money in your account

### **Email forwarding setup:**  

* Make sure that email forwarding on the account used to make the HIT (more than likely lab dartmouth email) because Turkers *will* contact you during a HIT if something goes wrong
* It's a good idea to have an email signature to appear more professional  

### **Auto Assignment approval setup:**

* Make sure that you have some reasonable timer Assignment auto-approval (e.g. 1hr - 24hrs is probably reasonable)
* This is important in case you need to wipe a database or debug an issue and no longer have access to completed assignments in Turkserver

### **HIT expiration setup (called Lifetime in TurkServer):**

- Make sure that you have a reasonable timer for when a HIT expires (this entirely depends on the nature of your study), i.e. how long it's visible for workers to be able to accept it
- Simple things might be just 24hrs or less (it's probably a good idea to run small batches at different times rather than a large batch all at once for multi-turker matching purposes and to more uniformly sample the Turker pool)
- This is also important in case you run into issues as noted above 

### **Assignment duration**

* Make sure to set this to something a little more than the length of your study
* This way if there are problems the a Turker's assignment will automatically end when this time is reached
