# GDPR - General Data Protection Regulation

- BASIC PRINCIPLES
- RIGHTS

### Basic principles

- Data minimisation (one should not collect more than necessary).
- integrity and confidentiality (all security measures to protect data that you
can think of + measures to guarantee that the data has not been inappropriately
modified)

### Rights

- "data subject" refers to the user/client.
- the right to erasure (the right to be forgotten/deleted from the system).
- right to restriction of processing (you still keep the data, but mark it as
"restricted" and don't touch it without further consent by the user)
- the right to data portability (the ability to export ones data in a
structured, commonly used and machine-readable format).
- the right to rectification (the ability to get personal data fixed).
- the right to be informed (getting human-readable information, rather than long
terms and conditions).
- the right of access (the user should be able to see all the data you have
about them).

## Exceptions

### More than 250 people company or do you process a lot of data?

- Keep a record of all types of processing activities carried out, including
transfers to processors (3rd parties) which includes cloud service providers.
- None of the other requirements of the regulation have an exception depending
on the organisation size.

## What is personal data?

- Any piece of information that can be used to uniquely identify a person, or
data that is about an already identified person.
- It's data that the user has explicitly provided.
- Also data you have collected about a person from 3rd parties, or based on a
persons activity on a site or a 3rd party site/service.


## Does any of what is discussed below have to be automated?

- No, the procedures and processes can be manual, they just have to be in a
reasonable time frame.


## Forgot me?

- Only applies if the data is collected by consent or based or based on what is
in the users best interest.
- Does not apply to data collected for legal obligation or for contract enforcement.
- It may be enough to make sure that the user is not longer identifiable in your
system you don't have to cascade delete all the users information.
- "Our data model does not allow it." is not an acceptable excuse.
- BE CAREFUL WHAT YOU PUT IN THE BLOCKCHAIN!
- Backups: You don't need to go through all your backups and "forget" the user.
However, if a backup is restored, you need to ensure that all users who have 
requested to be forgotten, are forgotten. Having "forgotten" data restored because 
a backup was restored is NOT an acceptable excuse.

## Notify 3rd parties for erasure

- If someone requests to be forgotten, you have to notify all 3rd parties you
shared their information with, to delete the information.
- You need to call the "forget me" end point, or trigger whatever process 3rd
parties have for the user to be forgotten.
- It is still your responsibility to make sure that the users details don't
appear in search results.
This only applies to public facing pages that are indexable by search engines,
while you may not be able to get Google to forget
a user existed on your system, you can make that page return a 404.

## Restrict processing

- This can be implemented as a backend admin panel, or a user setting. Meaning,
the process doesn't have to be automated.
- You can display a users some simple to read and understand information about
what the result of marking their profile as restricted will be.
- The users data should no longer be visible to the back-office staff or to the
public.

## Are there conditions for when the user can request to be forgotten or restrict
processing?

- Yes. The conditions are both broad and specific depending on the feature being
talked about. For example, for "restrict processing" they may request it if they 
feel the data is inaccurate, unlawfully obtained, or their feel we no longer need 
their data. This is beyond the scope of this discussion.

## Export data

- What "Data" is, depends on the use case for your product.
- You can provide the user with options as to all that they wish to export.
- The structure of the data is not strictly defined, but shouldn't violate the
users right to portability.
- Process does not have to be automatic, it can be manual, just has to be in a
reasonable timeframe.

## Allow users to edit their profile

- Should allow for rectification of all data, including that collected from 3rd
parties such as FB.
- In a scenario, where a users data has been indirectly collected, it should
still be modifiable as long as the user can prove that data relates to them.
- This process can also be manual.

## Consent checkboxes

- “I accept the terms and conditions” is no longer enough, clear yes/no checkboxes
for each “processing activity” that a users is agreeing to and, they should be
able to withdraw their consent at any time. This may mean enabling/disabling features
based on what the user has agreed to, or informing them that they can’t use or signup
for the service unless they agree to some/all of the conditions.
- If you are going to use the user’s data to train your ML models, you should
get consent for that as well (unless it’s for scientific purposes, which have special
treatment in the regulation).
- “legitimate interest” are also exempt:

> It is for the legal team to decide what a legitimate interest is, 
but direct marketing is included in that category, as well as any 
common sense processing relating to the business activity – e.g. 
if you collect addresses for shipping, it’s obviously a legitimate 
interest. So not all processing activities need consent checkboxes.
[QUOTE](https://techblog.bozho.net/gdpr-practical-guide-developers/)

## Contacting the user

- You can't contact the user through any means without the users approval.
- You need approval for each medium of communication or each type of communication depending on your business model.
- Fair use applies, for example if you need to verify the users email address.
- The user should be able to opt out of this communication.

## Re-request consent

- If someone agreed to your terms & conditions, you must get consent again in a
GDPR 
compliant manner.

## Right of access

- Similar to export my data. 
- This is optional
- Unregistered users should also be able to check what data exists on them. 
If unregistered users are being tracked in any manner, then they should be able 
to see what data is collected  on them. If a user is tracked anonymously, 
then there should be some way of the user checking their activity 
(such as search history).
- If an unregistered user is tracked using any identifiable information, they
should be able to use that to see what data is collected on them. 
- All rights above apply to these users.

## Age check (Article 8)

- You should collect information of your users ago, if they are below 16,
parental permission should be acquired.
- Reasonable effort is required.
- States can set age limits below 16, but no lower than 13.
- (Article 8) Paragraph 1 shall not affect the general contract law of Member
States such as the rules on the validity, formation or effect of a contract in relation
to a child.
- Some state can consider collecting data on underage children without consent highly 
illegal.

## Don't store data longer than necessary

- Applies to data collected for a specific reason.
- For e-commerce sites, this may even apply to 
names and address of anonymous users after the goods have been delivered.
- Delete or anonymise the data.

## Cookies 

- Long discussion, maybe next time.

## Technical stuff - not mandated, but considered good form.

- Encrypt the data in transit.
- Encrypt the data at rest.
- Encrypt your backups.
- Implement pseudonymization.
- Protect data integrity - broad statement.
Basically make sure you can detect if data has been changed. 
Something is better than nothing.
- Article 30 says that you should keep a record of all the types 
of activities that you use personal data for. 
(More specifics on this https://gdpr-info.eu/art-30-gdpr/)
- Log access to personal data
- Register all API consumers (No anonymous access to personal data).
- Don’t use data for purposes that the user hasn’t agreed with.
- Don’t log personal data.
- Don’t put fields on the registration/profile form that you don’t need.
- Don’t assume 3rd parties are compliant.
- Don’t assume having PCI / ISO XXX makes you compliant.
