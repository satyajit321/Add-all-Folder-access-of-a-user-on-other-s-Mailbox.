<p><strong>SYNOPSIS</strong><br /> Sample Script - use at your own risk, no warranties or guarantees.<br /> Checks Exchange mailbox permissions and adds read-only access for the specified mailbox user<br /> or distribution group. Evaluates each folder, including user created folders. If the <br /> permissions for any level of access are already set on a folder, no changes are made. Actions<br /> are recorded to a log file in the same folder as the script. The log file is named using the<br /> current date/time and the alias of the mailbox: ReadOnlyPermissions_&lt;mailbox&gt;_&lt;datetime&gt;.log</p>
<p><strong>DESCRIPTION</strong><br /> Sets read-only access permissions on the specified mailbox for the specified user or group.<br /> {Reviewer}= -AccessRights ReadItems,FolderVisible<br /> Total folders evaluated, might vary based on RBAC permissions on the administrator (Recovery,Purges etc.)<br /> But only standard and user folders actioned upon.</p>
<p><strong>PARAMETER Mailbox</strong><br /> Specify the mailbox to which permissions will be set.<br /> This required parameter can be in the form of email address or mailbox alias.</p>
<p><strong>PARAMETER User</strong><br /> Specify the user of group for which access rights will be set on the mailbox.</p>
<p><strong>EXAMPLE\USAGE</strong><br /> Add-ReadOnlyMailboxPermissions -Mailbox <a href="mailto:user1@contoso.com">user1@contoso.com</a> -User <a href="mailto:user2@contoso.com">user2@contoso.com</a><br /> This will add permissions for read-only access on <a href="mailto:user1@contoso.com"> user1@contoso.com</a> mailbox for user <a href="mailto:user2@contoso.com">user2@contoso.com</a></p>
<p>Even though this is testing against Exchange 2013, cmdlets havn't changed much since Exchange 2010. Hence should work there as well.</p>
<p>&nbsp;<br /> Updated\Modified by Satyajit321</p>
<p>&nbsp;<br /> NOTE:- This script&nbsp;is a&nbsp;revised&nbsp;version of&nbsp;Add-ReadOnlyMailboxPermissions.ps1 as mentioned in the references section. (After correcting Syntax errors and parameter mismatch and new logic.)</p>
<p>You can access the other half of the script that does exactly the opposite of what this does.</p>
<p>Remove all Folder access of a user on other's Mailbox:</p>
<p><a href="https://gallery.technet.microsoft.com/exchange/Removes-all-Folder-access-45cc1a4a">https://gallery.technet.microsoft.com/exchange/Removes-all-Folder-access-45cc1a4a</a></p>
<p>&nbsp;</p>
<p><strong>Sample Script Run:</strong></p>
<p>Add-ReadOnlyMailboxPermissions.ps1 -Mailbox User1 -User User2</p>
<p>&nbsp;</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>PowerShell</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">powershell</span>
<pre class="hidden">[PS] C:\Scripts&gt;.\Add-ReadOnlyMailboxPermissions.ps1 -Mailbox User1 -User User2
Processing actions to add read-only access rights for user User2 to mailbox User1
Setting AccessRights on folder User1:\ to FolderVisible
Successfully set AccessRights on folder User1:\
Folder User1:\Calendar already has Reviewer set for user User2
Skipping permissions change for this folder
Folder User1:\Contacts already has Reviewer set for user User2
Skipping permissions change for this folder
Folder User1:\Deleted Items already has Reviewer set for user User2
Skipping permissions change for this folder
Folder User1:\Drafts already has Reviewer set for user User2
Skipping permissions change for this folder
Setting AccessRights on folder User1:\Inbox to Reviewer
Successfully set AccessRights on folder User1:\Inbox
Folder User1:\Journal already has Reviewer set for user User2
Skipping permissions change for this folder
Folder User1:\Junk Email already has Reviewer set for user User2
Skipping permissions change for this folder
Folder User1:\Notes already has Reviewer set for user User2
Skipping permissions change for this folder
Folder User1:\Outbox already has Reviewer set for user User2
Skipping permissions change for this folder
Setting AccessRights on folder User1:\Sent Items to Reviewer
Successfully set AccessRights on folder User1:\Sent Items
Folder User1:\Tasks already has Reviewer set for user User2
Skipping permissions change for this folder
Processing complete. 12 total folders evaluated, 3 folders set, 9 folders skipped because permissions already set.
[PS] C:\Scripts&gt;
</pre>
<div class="preview">
<pre class="powershell">[<span class="powerShell__alias">PS</span>]&nbsp;C:\Scripts&gt;.\Add<span class="powerShell__operator">-</span>ReadOnlyMailboxPermissions.ps1&nbsp;<span class="powerShell__operator">-</span>Mailbox&nbsp;User1&nbsp;<span class="powerShell__operator">-</span>User&nbsp;User2&nbsp;
<span style="color: #339966;">Processing&nbsp;actions&nbsp;to&nbsp;add&nbsp;read<span class="powerShell__operator">-</span>only&nbsp;access&nbsp;rights&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;to&nbsp;mailbox&nbsp;User1&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\&nbsp;to&nbsp;FolderVisible&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\&nbsp;
Folder&nbsp;User1:\Calendar&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Folder&nbsp;User1:\Contacts&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Folder&nbsp;User1:\Deleted&nbsp;Items&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Folder&nbsp;User1:\Drafts&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Inbox&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Inbox&nbsp;
Folder&nbsp;User1:\Journal&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Folder&nbsp;User1:\Junk&nbsp;Email&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Folder&nbsp;User1:\Notes&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Folder&nbsp;User1:\Outbox&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Sent&nbsp;Items&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Sent&nbsp;Items&nbsp;
Folder&nbsp;User1:\Tasks&nbsp;already&nbsp;has&nbsp;Reviewer&nbsp;set&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;
Skipping&nbsp;permissions&nbsp;change&nbsp;<span class="powerShell__keyword">for</span>&nbsp;this&nbsp;folder&nbsp;
Processing&nbsp;complete.&nbsp;12&nbsp;total&nbsp;folders&nbsp;evaluated,&nbsp;3&nbsp;folders&nbsp;set,&nbsp;9&nbsp;folders&nbsp;skipped&nbsp;because&nbsp;permissions&nbsp;already&nbsp;set.&nbsp;
</span>[<span class="powerShell__alias">PS</span>]&nbsp;C:\Scripts&gt;&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Sample Output Log:</strong></p>
<p>ReadOnlyPermissions-User1-20150519-213632.log</p>
<p>&nbsp;</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>PowerShell</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">powershell</span>
<pre class="hidden">Processing actions to add read-only access rights for user User2 to mailbox User1
Setting AccessRights on folder User1:\ to FolderVisible
Successfully set AccessRights on folder User1:\
Setting AccessRights on folder User1:\Calendar to Reviewer
Successfully set AccessRights on folder User1:\Calendar
Setting AccessRights on folder User1:\Contacts to Reviewer
Successfully set AccessRights on folder User1:\Contacts
Setting AccessRights on folder User1:\Deleted Items to Reviewer
Successfully set AccessRights on folder User1:\Deleted Items
Setting AccessRights on folder User1:\Drafts to Reviewer
Successfully set AccessRights on folder User1:\Drafts
Setting AccessRights on folder User1:\Inbox to Reviewer
Successfully set AccessRights on folder User1:\Inbox
Setting AccessRights on folder User1:\Journal to Reviewer
Successfully set AccessRights on folder User1:\Journal
Setting AccessRights on folder User1:\Junk Email to Reviewer
Successfully set AccessRights on folder User1:\Junk Email
Setting AccessRights on folder User1:\Notes to Reviewer
Successfully set AccessRights on folder User1:\Notes
Setting AccessRights on folder User1:\Outbox to Reviewer
Successfully set AccessRights on folder User1:\Outbox
Setting AccessRights on folder User1:\Sent Items to Reviewer
Successfully set AccessRights on folder User1:\Sent Items
Setting AccessRights on folder User1:\Tasks to Reviewer
Successfully set AccessRights on folder User1:\Tasks
Processing complete. 12 total folders evaluated, 12 folders set, 0 folders skipped because permissions already set.
</pre>
<div class="preview">
<pre class="powershell">Processing&nbsp;actions&nbsp;to&nbsp;add&nbsp;read<span class="powerShell__operator">-</span>only&nbsp;access&nbsp;rights&nbsp;<span class="powerShell__keyword">for</span>&nbsp;user&nbsp;User2&nbsp;to&nbsp;mailbox&nbsp;User1&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\&nbsp;to&nbsp;FolderVisible&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Calendar&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Calendar&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Contacts&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Contacts&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Deleted&nbsp;Items&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Deleted&nbsp;Items&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Drafts&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Drafts&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Inbox&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Inbox&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Journal&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Journal&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Junk&nbsp;Email&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Junk&nbsp;Email&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Notes&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Notes&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Outbox&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Outbox&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Sent&nbsp;Items&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Sent&nbsp;Items&nbsp;
Setting&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Tasks&nbsp;to&nbsp;Reviewer&nbsp;
Successfully&nbsp;set&nbsp;AccessRights&nbsp;on&nbsp;folder&nbsp;User1:\Tasks&nbsp;
Processing&nbsp;complete.&nbsp;12&nbsp;total&nbsp;folders&nbsp;evaluated,&nbsp;12&nbsp;folders&nbsp;set,&nbsp;0&nbsp;folders&nbsp;skipped&nbsp;because&nbsp;permissions&nbsp;already&nbsp;set.&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p>&nbsp;</p>
<p><strong>Referenes:</strong></p>
<p>&nbsp;<br /> Add-ReadOnlyMailboxPermissions.ps1:<br /> <a href="http://gallery.technet.microsoft.com/exchange/Add-Read-Only-Access-to-6e080379">http://gallery.technet.microsoft.com/exchange/Add-Read-Only-Access-to-6e080379</a></p>
<p>Remove all Folder access of a user on other's Mailbox:</p>
<p><a href="https://gallery.technet.microsoft.com/exchange/Removes-all-Folder-access-45cc1a4a">https://gallery.technet.microsoft.com/exchange/Removes-all-Folder-access-45cc1a4a</a></p>
<p>&nbsp;</p>
<p>Remove-MailboxFolderPermission:<br /> <a href="https://technet.microsoft.com/en-us/library/dd351181(v=exchg.150).aspx">https://technet.microsoft.com/en-us/library/dd351181(v=exchg.150).aspx</a></p>
<p><br /> Exchange 2010: And then there is the long awaited cmdlet Add-MailboxFolderPermission<br /> <a href="http://blogs.technet.com/b/ilvancri/archive/2009/11/24/exchange-2010-and-then-there-is-the-long-awaited-cmdlet-add-mailboxfolderpermission.aspx">http://blogs.technet.com/b/ilvancri/archive/2009/11/24/exchange-2010-and-then-there-is-the-long-awaited-cmdlet-add-mailboxfolderpermission.aspx</a></p>
<p>&nbsp;<br /> Exchange 2007/2010/2013 &ndash; Using Get-MailboxFolderPermissions to export MAPI permissions of folders for a given mailbox<br /> blogs.technet.com/b/samdrey/archive/2014/03/06/exchange-2007-2010-2013-using-get-mailboxfolderpermissions-to-export-mapi-permissions-of-folders.aspx</p>
