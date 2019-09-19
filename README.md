# Autocomplete-in-Salesforce-using-Jquery

#### An autocomplete component which filter list of Accounts. On click of an account, it displays the account details below the component. Under the account detail, it has an option to enter text and Post post on that on Account chatter

#### Code Walkthrough:
In Auto Complete functionality I have created Auto Complete
Component. In this component I am using JQuery JS and CSS for autocomplete which is
added in Static Resource. In apex class of Auto Complete Component, I have created
one method with annotation as RemoteAction which can be accessed directly from
JavaScript and this method executes SOSL query on all fields of Account object to search
for a particular string. In visualforce page I am using input field and JavaScript method to
autoComplete this input field. In that JavaScript method I am calling RemoteAction
method of my apex class with searched text and that will return a List of
AccountWrapper Class object (I have create one AccountWrapper class that will have
label and value fields which will store AccountId in value field and AccountName in label
Field). JavaScript then binds that list with the auto complete suggestions. When we
select any Account from the suggestion our JavaScript method of Component calls the
javascript method of VF page from where this component is called. Why we require
this? To intimate the Visualforce page that user has selected one Account from auto
complete field so showcase all the details for that Account. When we pass the Account
Id from component JavaScript to VF page JavaScript, our VF page JavaScript calls
actionFunction to save that accountId in a variable and calling a method. This method
executes a SOQL query to get details of that Account Id and renders the View Account
and Add Chatter post sections will all the data. On click on Post button in Add Chatter
post grid I am posting chatter message using FeedItem and passing the Account Id and
message body.
