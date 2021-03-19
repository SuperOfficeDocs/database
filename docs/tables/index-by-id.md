---
uid: database-table-listing-by-number
title: Database table listing by table ID
description: Lists all tables in the database by table ID.
so.generated: true
keywords:
  - "database"
so.date: 19.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# Database tables by [name](index.md) | **number** 

> [!NOTE]
> Most table numbers are fixed, but could be different between databases - depends on whether there are custom 3rd party tables.

| Number | Name | Description |
|----|-----|----|
|0| [sequence](sequence.md) |next_id to be used for each table|
|1| [company](company.md) |Information on license and owner of this SuperOffice database. This table should only have 1 row. This table contains encrypted license information. Changing it will disable login for all users and require you to restore the database from backup.|
|2| [associate](associate.md) |Employees, resources and other users - except for External persons|
|3| [associategrouplink](associategrouplink.md) |User group link table for Associate, for MDO item hiding|
|4| [associateheadinglink](associateheadinglink.md) |Heading link table for associate for display only. Supportive table, used for grouping and filtering on lists. |
|5| [contact](contact.md) |Companies and Organizations.   This table features a special record containing information about the contact that owns the database.  |
|6| [person](person.md) |Persons in a company or an organizations. All associates have a corresponding person record|
|7| [address](address.md) |Contact and Person addresses|
|8| [phone](phone.md) |Contact and Person phonenumbers (+fax)|
|9| [appointment](appointment.md) |Tasks, appointments, followups, phone calls; and documents (document_id != 0). An appointment always has a corresponding record in VisibleFor specifying who may see this. |
|10| [document](document.md) |Documents, this table is an extension of the Appointment table.  There is always a corresponding appointment record; the relation between appointment and document is navigable in both directions. A document-type appointment record always has a corresponding document record and a record in VisibleFor specifying who may see this.  |
|11| [project](project.md) |Projects|
|12| [projectmember](projectmember.md) |Project members. Link-table between person and project|
|13| [sale](sale.md) |Sales  For every Sale record edited through the SuperOffice GUI, a copy of the previous version of the record will be saved in the SaleHist table. This also applies to editing done through the SaleModel COM interface, but not to editing done through the OLE DB Provider or other channels.  |
|14| [contactinterest](contactinterest.md) |Link-table between contact and interests in ContInt|
|15| [personinterest](personinterest.md) |Note: If you add or remove rows in this table, you will need to update the interestCount field in the person table accordingly. This field should always reflect the number of interest records a person has, to enable the correct setting of the interest indicator on the tab in the person dialog.  Replication note: The combination of person_id and pinterest_idx is unique. If a duplicate is made on a replicated database, the system will replace the record in the target database with the one derived from the source database during replication. Therefore, do not assume that a record in this table will retain its ID indefinitely, even if the person keeps the interest.|
|16| [ziptocity](ziptocity.md) |Zip codes and city names. Zip codes used during address entry. You will find more information about addressformat on http://techdoc.superoffice.com |
|17| [redletterday](redletterday.md) |Red letter days for calendar (holidays, birthday of king etc)|
|18| [text](text.md) |Long text fields from all over the system|
|19| [country](country.md) |Country information|
|20| [countrygrouplink](countrygrouplink.md) |User group link table for Country, for MDO item hiding|
|21| [countryheadinglink](countryheadinglink.md) |Heading link table for Country, for MDO headers|
|22| [preference](preference.md) |Not quite obsolete preference table; historical info mostly. From 6.1 this table now holds an upgrade stamp.|
|23| [selection](selection.md) |Selections|
|24| [selectionmember](selectionmember.md) |Selection detail table  Each row in a selection is represented by one record in this table. Contact_id is always filled in, person_id is optional, but if used, must point to a person belonging to the contact in contact_id.|
|25| [sorpublishgrouplink](sorpublishgrouplink.md) |Link table used for filtering reports by user group|
|26| [quoteconnection](quoteconnection.md) |Primary key in the CRM database. Definition of a connection to an external system, for the Quote system.|
|27| [quoteconnectionaccess](quoteconnectionaccess.md) |Access control for Quote Connections|
|28| [activeuser](activeuser.md) |Currently logged-on users. This table contains encrypted license information.  Changing it may disable login for all users and require intervention by SuperOffice support. Recommended use: for determining who is logged on, at what location, etc.|
|29| [traveltransactionlog](traveltransactionlog.md) |Log of all updates made to the database, that need to be replicated.|
|30| [travelgeneratedtransaction](travelgeneratedtransaction.md) |Record of all generated replication data files from this database (*.dwn files from mother database to child, *.up from child database to mother)|
|31| [traveller](traveller.md) |Associates traveling out from this database|
|32| [travelcurrent](travelcurrent.md) |Information about this database and its place in the hierarchy|
|33| [travelgenerateddatabase](travelgenerateddatabase.md) |Information about all databases generated from this database|
|34| [quote](quote.md) |Quote root level, at most one per Sale, always connected to one Sale|
|35| [udcontactsmall](udcontactsmall.md) |User-defined fields for contact|
|36| [udcontactlarge](udcontactlarge.md) |User-defined fields for contact (long strings)|
|37| [mergemovelog](mergemovelog.md) |Log of merge and move operations (person, contact, project)|
|38| [area](area.md) |Definition of an Area (database subset for satellite and travel)|
|39| [quoteversion](quoteversion.md) |There may be multiple Versions of a Quote, with one of them active|
|40| [areauserassignment](areauserassignment.md) |Link table indicating which users actually reside in this area.|
|41| [areauserinclusion](areauserinclusion.md) |Link table incidated whose data should be included in this area. If Include all data in Area (no filtering) is ticket then there will be no rows for this area in this table.|
|42| [satellite](satellite.md) |Definition of Satellites|
|43| [travelidmapping](travelidmapping.md) |Mapping of primary keys between Travel databases and the mother database  All travel database transactions get a high id to be able to see that this entry came from a database outside the central database. When update files are read into the central database, they get a normal low id. This table remembers the high travel id to map it to the low central id as long as this travel user is travelling. |
|44| [freetextstopwords](freetextstopwords.md) |Here are the words that can be excluded from Free Text Search by using the FreeTextAdmin. The words that appear here will not be found in FreeTextWords and typically include &quot;are&quot;, &quot;this&quot;, &quot;that&quot;, and so on - words that occur frequently, but are not useful for searching.  The more (good) stop words you have, the smaller the index will be.|
|45| [freetextwords](freetextwords.md) |This table contains the word list (automatically updated by the indexer) for the free-text search. Words are in UPPERCASE and truncated to 9 significant characters. Indexed words, dynamically updated by the freetext index|
|46| [freetextindex](freetextindex.md) |This is the index table for the free text search function. Each word in FreeTextWords can have multiple occurrences in this table. Each record in this table points to one occurrence of the word, and points to both the table in which the word occurs (which might be contact or text), and also a pointer to the owner table (which is one of contact, person, project, appointment or sale). |
|47| [quotealternative](quotealternative.md) |Quote Version is made up of one or more Alternatives. One of 1..n possible alternatives in a Quote Version. The reason we have alternatives is that a quote can say to a customer, “we can solve you problem in two (or more) different ways, with different technology and sideeffects (and price)”. An Alternative may have discounts on the total amount. The Alternative tracks whether the user on the order level entered the Discount , Earning amount or the TotalPrice fields so that the discount and earning and total can be re-calculated correctly when Quote Lines are added or changed.|
|48| [relationdefinition](relationdefinition.md) |Definition of a relation. This table defines the relations that can exist in the database. Each relation has an active text and a passive text. The table RelationTarget specifies which pairs of tables this relation can connect.  Use of the active and passive texts is dependent on which direction the relation is viewed in, e.g., active text = &quot;Owns&quot; and passive text = &quot;Is owned by&quot;.|
|49| [reldefgrouplink](reldefgrouplink.md) |User group link table for RelDef, for MDO item hiding|
|50| [reldefheadinglink](reldefheadinglink.md) |Heading link table for RelDef, for MDO headers|
|51| [relationtarget](relationtarget.md) |Definition of targets for a relation. Links a relation definition (RelDef) to source and target tables. In general, a relation can be created between any pair of tables. This table is used for specifying which table pairs a particular relation can be used for. A relation definition should have at least one row in this table, and can have more. Note: The 5.0 Maintenance and GUI only support contact and person as valid values for the source_table and destination_table fields, in any combination. Other relations will not be shown, and relation definitions pointing to other tables will not be editable from the Maintenance GUI; however, nothing will crash.|
|52| [relations](relations.md) |Instance of a relation, in principle between any two records, as long as they are defined in RelationDefinition. All instances of relations are held in this table; their definitions are in the RelDef table (RelDef + RelTarg define which relations you can have, this table contains the relations the user has actually entered). From 6.1 all links between appointments, sales and documents are also stored in this tabel.|
|53| [history](history.md) |History lists for lists and searchable controls. Maintains history for Navigator or other search (find dialogs). A single table may have more than one record here, as indicated by the extra_id field. The HistorySize (preference may be set in maintenance client) defines how many records you can have in a history list.|
|54| [url](url.md) |Unified Resource Locators, URL to contacts, persons or projects.|
|55| [email](email.md) |Email addresses for contacts, projects and persons|
|56| [userpreference](userpreference.md) |Preference system. If deflevel is set to 5; the user may change the preferences|
|57| [addressformat](addressformat.md) |Address formats for GUI and labels. See more information: Addressformat on http://techdoc.superoffice.com|
|58| [heading](heading.md) |Heading items for all MDO lists, lists that are grouped and filtered.|
|59| [usergroup](usergroup.md) |Secondary user groups|
|60| [usergrouplink](usergrouplink.md) |Link table between associate and usergroup, specifies secondary group membership. From SIX an associate may belong to more than one usergroup. Http://techdoc.superoffice.com has more information about how roles are implemented.|
|61| [business](business.md) |Business list table|
|62| [businessgrouplink](businessgrouplink.md) |User group link table for Business, for MDO item hiding|
|63| [businessheadinglink](businessheadinglink.md) |Heading link table for Business, for MDO headers|
|64| [category](category.md) |Category list table|
|65| [categorygrouplink](categorygrouplink.md) |User group link table for Category, for MDO item hiding|
|66| [categoryheadinglink](categoryheadinglink.md) |Heading link table for Category, for MDO headers|
|67| [task](task.md) |Task list table, activity types, like Phone, Meeting|
|68| [taskgrouplink](taskgrouplink.md) |User group link table for Task, for MDO item hiding|
|69| [taskheadinglink](taskheadinglink.md) |Heading link table for Task, for MDO headers|
|70| [contint](contint.md) |ContInt list table. List-text of all valid contact interest types.|
|71| [contintgrouplink](contintgrouplink.md) |User group link table for ContInt, for MDO item hiding|
|72| [contintheadinglink](contintheadinglink.md) |Heading link table for ContInt, for MDO headers|
|73| [persint](persint.md) |PersInt list table. List of Person interests.|
|74| [persintgrouplink](persintgrouplink.md) |User group link table for PersInt, for MDO item hiding|
|75| [persintheadinglink](persintheadinglink.md) |Heading link table for PersInt, for MDO headers|
|76| [perspos](perspos.md) |PersPos list table. Contact person position list|
|77| [persposgrouplink](persposgrouplink.md) |User group link table for PersPos, for MDO item hiding|
|78| [persposheadinglink](persposheadinglink.md) |Heading link table for PersPos, for MDO headers|
|79| [priority](priority.md) |Priority list table. Used with appointments: low, high.|
|80| [prioritygrouplink](prioritygrouplink.md) |User group link table for Priority, for MDO item hiding|
|81| [priorityheadinglink](priorityheadinglink.md) |Heading link table for Priority, for MDO headers|
|82| [prob](prob.md) |Prob list table. Probability, used in  sales .|
|83| [probgrouplink](probgrouplink.md) |User group link table for Prob, for MDO item hiding|
|84| [probheadinglink](probheadinglink.md) |Heading link table for Prob, for MDO headers|
|85| [projtype](projtype.md) |ProjType list table. List of valid Project types.|
|86| [projtypegrouplink](projtypegrouplink.md) |User group link table for ProjType, for MDO item hiding|
|87| [projtypeheadinglink](projtypeheadinglink.md) |Heading link table for ProjType, for MDO headers|
|88| [projstatus](projstatus.md) |ProjStatus list table. Project status|
|89| [projstatusgrouplink](projstatusgrouplink.md) |User group link table for ProjStatus, for MDO item hiding|
|90| [projstatusheadinglink](projstatusheadinglink.md) |Heading link table for ProjStatus, for MDO headers|
|91| [pmembtype](pmembtype.md) |PMembType list table. List text of titles (member types) for project members.|
|92| [pmembtypegrouplink](pmembtypegrouplink.md) |User group link table for PMembType, for MDO item hiding|
|93| [pmembtypeheadinglink](pmembtypeheadinglink.md) |Heading link table for PMembType, for MDO headers|
|94| [mrmrs](mrmrs.md) |MrMrs list table. List of salutations.|
|95| [mrmrsgrouplink](mrmrsgrouplink.md) |User group link table for MrMrs, for MDO item hiding|
|96| [mrmrsheadinglink](mrmrsheadinglink.md) |Heading link table for MrMrs, for MDO headers|
|97| [credited](credited.md) |Credited list table. List of who is to be credited for the sale.|
|98| [creditedgrouplink](creditedgrouplink.md) |User group link table for Credited, for MDO item hiding|
|99| [creditedheadinglink](creditedheadinglink.md) |Heading link table for Credited, for MDO headers|
|100| [source](source.md) |Source list table. Source for sale (list)|
|101| [sourcegrouplink](sourcegrouplink.md) |User group link table for Source, for MDO item hiding|
|102| [sourceheadinglink](sourceheadinglink.md) |Heading link table for Source, for MDO headers|
|103| [reason](reason.md) |Reason list table. Why we lost the sale (list)|
|104| [reasongrouplink](reasongrouplink.md) |User group link table for Reason, for MDO item hiding|
|105| [reasonheadinglink](reasonheadinglink.md) |Heading link table for Reason, for MDO headers|
|106| [searchcat](searchcat.md) |SearchCat list table|
|107| [searchcatgrouplink](searchcatgrouplink.md) |User group link table for SearchCat, for MDO item hiding|
|108| [searchcatheadinglink](searchcatheadinglink.md) |Heading link table for SearchCat, for MDO headers|
|109| [comptr](comptr.md) |Comptr list table. List of all possible competitors (sale).|
|110| [comptrgrouplink](comptrgrouplink.md) |User group link table for Comptr, for MDO item hiding|
|111| [comptrheadinglink](comptrheadinglink.md) |Heading link table for Comptr, for MDO headers|
|112| [currency](currency.md) |Currency list table|
|113| [currencygrouplink](currencygrouplink.md) |User group link table for Currency, for MDO item hiding|
|114| [currencyheadinglink](currencyheadinglink.md) |Heading link table for Currency, for MDO headers|
|115| [reasonsold](reasonsold.md) |Why was the sale marked as sold (why did we succeed)|
|116| [reasonsoldgrouplink](reasonsoldgrouplink.md) |User group link table for ReasonSold, for MDO item hiding|
|117| [reasonsoldheadinglink](reasonsoldheadinglink.md) |Heading link table for ReasonSold, for MDO headers|
|118| [saletypecat](saletypecat.md) |Category for sale type|
|119| [saletypecatgrouplink](saletypecatgrouplink.md) |User group link table for SaleTypeCat, for MDO item hiding|
|120| [saletypecatheadinglink](saletypecatheadinglink.md) |Heading link table for SaleTypeCat, for MDO headers|
|121| [salestakeholder](salestakeholder.md) |Stakeholders in the sale, very similar to project members|
|122| [stakeholderrole](stakeholderrole.md) |Role a stakeholder has in a sale|
|123| [stakeholderrolegrouplink](stakeholderrolegrouplink.md) |User group link table for StakeholderRole, for MDO item hiding|
|124| [stakeholderroleheadinglink](stakeholderroleheadinglink.md) |Heading link table for StakeholderRole, for MDO headers|
|125| [suggestedappointment](suggestedappointment.md) |Defines a suggested appointment for use in a Sale Guide or Project Guide|
|126| [suggesteddocument](suggesteddocument.md) |Unique owner of a set of licensed modules|
|127| [quoteline](quoteline.md) |One line in a QuoteAlternative. QuoteLines are mainly information copied from the Products provider. Products information is sometimes edited by the user before being included in the quote, so most information is duplicated from Product rather than referenced directly.|
|128| [pricelist](pricelist.md) |List of prices, cached from an ERP system|
|129| [product](product.md) |One Product, member of one price list|
|130| [doctmpl](doctmpl.md) |DocTmpl list table. Describes templates available for writing new documents.|
|131| [doctmplgrouplink](doctmplgrouplink.md) |User group link table for DocTmpl, for MDO item hiding|
|132| [doctmplheadinglink](doctmplheadinglink.md) |Heading link table for DocTmpl, for MDO headers|
|133| [extapp](extapp.md) |ExtApp list table. Applications startable from SuperOffice|
|134| [extappgrouplink](extappgrouplink.md) |User group link table for ExtApp, for MDO item hiding|
|135| [extappheadinglink](extappheadinglink.md) |Heading link table for ExtApp, for MDO headers|
|136| [udlist](udlist.md) |List table for user-defined lists, contains all user-defined lists. Note - MDO mode for userdefinede lists are either turned on or off, you may not have it on for one userdefined list and off for the others.|
|137| [udlistgrouplink](udlistgrouplink.md) |User group link table for UDList, for MDO item hiding. Note - MDO mode for userdefinede lists are either turned on or off, you may not have it on for one userdefined list and off for the others.|
|138| [udlistheadinglink](udlistheadinglink.md) |Heading link table for UDList, for MDO headers. Note - MDO mode for userdefinede lists are either turned on or off, you may not have it on for one userdefined list and off for the others.|
|139| [udlistdefinition](udlistdefinition.md) |List table that contains the list of user-defined lists, as well as system-defined lists. The list items are stored in the UDList table. |
|140| [udpersonsmall](udpersonsmall.md) |User-defined fields|
|141| [udpersonlarge](udpersonlarge.md) |User-defined fields|
|142| [udprojectsmall](udprojectsmall.md) |User-defined fields|
|143| [udprojectlarge](udprojectlarge.md) |User-defined fields. During conversion of user defined fields the data is stored in this table.|
|144| [udtempsmall](udtempsmall.md) |User-defined fields. During conversion of user defined fields the data is stored in this table.|
|145| [udtemplarge](udtemplarge.md) |User-defined fields|
|146| [udeffield](udeffield.md) |Definition table for user-defined fields; one row in this table corresponds to one generation of one field. The user defined fields that are in use, and earlier versions of user defined fields. ColumnId refers to the field type; see UDXXXSmall or UDXXXLarge for the referring ID.  Preferences prefsection=&apos;System&apos;, prefkey=&apos;CurrentUdefVersioncontact&apos;  (or CurrentUdefVersionperson, project, sale), gives you the current version of user defined fields.  prefkey=&apos;AdminUdefVersion&lt;...&gt;&apos; gives you the current version that&apos;s being edited. If Current version = admin version, no editing has been done since the last Publish of user defined field was performed.|
|147| [udeffieldgl](udeffieldgl.md) |User group link table for UDefField, for MDO item hiding|
|148| [cachetables](cachetables.md) |Specifies which tables should be cached to local files (or otherwise), generally these are the lists and other low-frequency-of-change tables. Contains the ID of any tables cached in SOCache. The files are binary and called &lt;tablename&gt;.bin.  &lt;Shift&gt;+&lt;F5&gt; throws all cache files. |
|149| [saletype](saletype.md) |Type of sale - large solution, incremental, whatever fits the organization|
|150| [saletypegrouplink](saletypegrouplink.md) |User group link table for SaleType, for MDO item hiding|
|151| [saletypeheadinglink](saletypeheadinglink.md) |Heading link table for SaleType, for MDO headers|
|152| [taborder](taborder.md) |Order of tabs within a tab control, if configured by a user|
|153| [systemevent](systemevent.md) |System events, such as freetext rebuild, SAINT rebuild and such. Makes broadcasts to keep its siblings and clients updated. |
|154| [reasonstalled](reasonstalled.md) |Why was the sale marked as stalled|
|155| [reasonstalledgrouplink](reasonstalledgrouplink.md) |Link table for ReasonStalled, for MDO item hiding|
|156| [reasonstalledheadinglink](reasonstalledheadinglink.md) |Heading link table for ReasonStalled, for MDO headers|
|157| [salehist](salehist.md) |Mirror image of the Sale table, providing a full transaction history. Every time you edit a sale, the previous record of the sale is moved here. |
|158| [udsalesmall](udsalesmall.md) |User-defined fields|
|159| [udsalelarge](udsalelarge.md) |User-defined fields|
|160| [saletypestagelink](saletypestagelink.md) |Many-many link table between sale type and stage; and an anchor point for guide items|
|161| [olesubject](olesubject.md) |Control data table for the OLE DB Provider|
|162| [olesubjecttext](olesubjecttext.md) |Control data table for the OLE DB Provider|
|163| [oleview](oleview.md) |Control data table for the OLE DB Provider|
|164| [oleviewtext](oleviewtext.md) |Control data table for the OLE DB Provider|
|165| [olefield](olefield.md) |Control data table for the OLE DB Provider|
|166| [olefieldtext](olefieldtext.md) |Control data table for the OLE DB Provider|
|167| [ownercontactlink](ownercontactlink.md) |Table specifying which contacts can own associates.  All contacts that have rows in this table (i.e. rows with contact_id pointing to them) will be offered as associate owners in the maintenance client and as candidate Satellite owners. Such contacts have restrictions on editing and deletion to protect database consistency. |
|168| [fieldlabel](fieldlabel.md) |Field label override table, makes it possible to override internal string resources. Define your own text for the panels in SuperOffice, e.g. rename Project to Cars in SOAdmin - System Options - Labels  This table contains controlling data for the string substitution mechanism. There is one row in this table for each label or string that can be substituted; the active field indicates whether the string is actually being substituted or not. Initially, all rows have this field set to 0. The table is loaded with initial data during database setup.  Only SuperOffice Development has the necessary expertise to safely add rows to this table.  If a row has active = 1, the table LocaleText should contain one or more rows pointing back to this table, with the actual text to be used. |
|169| [localetext](localetext.md) |Multi-language text items. Used for user-defined field labels. Must be assigned correct name to match the language they start SuperOffice in.  This table should be viewed in conjunction with FieldLabel. If a row in FieldLable has active = 1 this table will need to contain at least one row with the same resourceId as the FieldLabel row. The language id can be either 0 or one of the Windows language ID&apos;s; SuperOffice will pick the correct language on startup according to the user settings. If a label cannot be found with the given language and also not with language 0, it will not be substituted. |
|170| [reporterlistdef](reporterlistdef.md) |Reporter definitions|
|171| [refcounts](refcounts.md) |Number counter for all tables that generate numbers, e.g. templates, contacts...   This table is used for the number allocation system and should not be confused with sequence, used for allocating internal ID&apos;s. This table is replicated during generation of satellites and during local update for travellers, using special logic. By default it contains rows for the SuperOffice standard counters, including one row for each DocTemplate record.  It is permissible to add new rows to this table, and such records are maintainable through the Maintenance client.  Changing the contents of the standard records is not recommended. |
|172| [refcountrange](refcountrange.md) |Number allocation system, for keeping track of ranges of numbers loaned out to travel and satellite databases|
|173| [sortemplate](sortemplate.md) |SuperOffice reporter data|
|174| [sorpublish](sorpublish.md) |SuperOffice reporter data|
|175| [sorcriteria](sorcriteria.md) |SuperOffice reporter data|
|176| [soroperators](soroperators.md) |SuperOffice reporter data|
|177| [sorsection](sorsection.md) |SuperOffice reporter data|
|178| [sorfct](sorfct.md) |SuperOffice reporter data|
|179| [sorfield](sorfield.md) |SuperOffice reporter data|
|180| [sorlabellayout](sorlabellayout.md) |SuperOffice reporter data|
|181| [foreignapp](foreignapp.md) |Top level of Foreign Key system|
|182| [foreigndevice](foreigndevice.md) |Middle level of Foreign Key system|
|183| [foreignkey](foreignkey.md) |Foreign Key - enables storage of arbitrary extra key information for every table/row in SuperOffice. You may use this table to store your extra information instead of using the dictionary SDK to create your own tables.|
|184| [prefdesc](prefdesc.md) |Preference description, drives the Preference GUI. Maintenance client - controls all preferences in SuperOffice. You find an overview off all standard preference on http://techdoc.superoffice.com.  May be used by third-party developers to add system preferences to be updated from SuperOffice Maintenance client, instead of ini-files. |
|185| [prefdescline](prefdescline.md) |Preference description - multiple choice line - drives the Preference GUI. May be used by third-party developers to add system preferences to be updated from SuperOffice Maintenance client, instead of ini-files.|
|186| [importobject](importobject.md) |Import object types - see localetext for names.|
|187| [importfield](importfield.md) |Import object types - see localetext for names|
|188| [importrelation](importrelation.md) |Relations between import objects|
|189| [importdefault](importdefault.md) |Defaults for import fields/objects|
|190| [usagestats](usagestats.md) |Usage statistics|
|191| [role](role.md) |User roles for role-based security, names and tooltips are in LocaleText. For more information regarding role based security, see http://techdoc.superoffice.com|
|192| [userrolelink](userrolelink.md) |Link between user role and user|
|193| [functionright](functionright.md) |Functional right definition|
|194| [functionrightrolelink](functionrightrolelink.md) |Functional right definition|
|195| [dataright](dataright.md) |Data right definition|
|196| [visiblefor](visiblefor.md) |Visible for rights, who may see this appointment/document, sale,  salehist or selection|
|197| [countervalue](countervalue.md) |Visible for rights|
|198| [statusdef](statusdef.md) |Status definitions. Name and description are in LocaleText for internationalization|
|199| [statusvalue](statusvalue.md) |Values for statuses|
|200| [publish](publish.md) |Publishing system for external users|
|201| [searchcriteria](searchcriteria.md) |Criteria storage for Selection and other Find mechanisms|
|202| [searchcriteriagroup](searchcriteriagroup.md) |Criteria storage for Selection and other Find mechanisms|
|203| [searchcriterion](searchcriterion.md) |Criteria storage for Selection and other Find mechanisms|
|204| [searchcriterionvalue](searchcriterionvalue.md) |Criteria storage for Selection and other Find mechanisms|
|205| [binaryobject](binaryobject.md) |Binary objects, i.e., blobs. Used for images, documents, SuperOffice inbox mail  and other large binary items|
|206| [binaryobjectlink](binaryobjectlink.md) |Link table, connects a BinaryObject with one or more owners|
|207| [recurrencerule](recurrencerule.md) |The recurrency pattern for a recurring event. Each recurring event has an appointment.recurrenceRuleId pointing to its pattern.|
|208| [winpossize](winpossize.md) |Stores the position and size of each window, so they can be shown in the same place again|
|209| [superlistcolumnsize](superlistcolumnsize.md) |Stores the relative size (in percent) or in characters of a column in a SuperList|
|210| [languageinfo](languageinfo.md) |Information about languages, from ISO standards and related information|
|211| [languageinfocountry](languageinfocountry.md) |Many-many link between countries and languages, to give intelligent choices for language|
|212| [moduleowner](moduleowner.md) |Unique owner of a set of licensed modules|
|213| [projecttypestatuslink](projecttypestatuslink.md) |Many-many link table between project type and status, similar to sale type-stage link; and an anchor point for guide items|
|214| [diaryview](diaryview.md) |Configuration of a multi-user diary view|
|215| [diaryviewrow](diaryviewrow.md) |Configuration of a multi-user diary view|
|216| [intent](intent.md) |Intent list for SAINT. More information regarding SuperOffice Sales Intelligence on http://techdoc.superoffice.com |
|217| [intentgrouplink](intentgrouplink.md) |User group link table for Intent, for MDO item hiding|
|218| [intentheadinglink](intentheadinglink.md) |Heading link table for Intent, for MDO headers|
|219| [salutation](salutation.md) |Academic title for Person|
|220| [salutationgrouplink](salutationgrouplink.md) |User group link table for Salutation, for MDO item hiding|
|221| [salutationheadinglink](salutationheadinglink.md) |Heading link table for Salutation, for MDO headers|
|222| [rejectreason](rejectreason.md) |Rejection reason (suggested) for bookings|
|223| [rejectreasongrouplink](rejectreasongrouplink.md) |User group link table for Comptr, for MDO item hiding|
|224| [rejectreasonheadinglink](rejectreasonheadinglink.md) |Heading link table for RejectReason, for MDO headers|
|225| [amountclass](amountclass.md) |Amount Class list for SuperOffice Sales Intelligence (Saint) - used to group sales by amounts, into bins (low --&gt; high) called amount classes. More information regarding SuperOffice Sales Intelligence on http://techdoc.superoffice.com |
|226| [amountclassgrouplink](amountclassgrouplink.md) |User group link table for AmountClass, for MDO item hiding|
|227| [amountclassheadinglink](amountclassheadinglink.md) |Heading link table for AmountClass, for MDO headers|
|228| [udappntsmall](udappntsmall.md) |User-defined fields|
|229| [udappntlarge](udappntlarge.md) |User-defined fields|
|230| [uddocsmall](uddocsmall.md) |User-defined fields|
|231| [uddoclarge](uddoclarge.md) |User-defined fields|
|232| [audiencevisibility](audiencevisibility.md) |How projects (or whatever) should be made visible in audience|
|233| [externalevent](externalevent.md) |The definition of projects as events in Audience (or other Collaborative apps)|
|234| [audiencelayout](audiencelayout.md) |One layout (of webparts and other stuff) for an audience instance|
|235| [audiencelayoutlink](audiencelayoutlink.md) |Link between an audience layout and some target grouping table - might be Role or Category|
|236| [audienceconfig](audienceconfig.md) |Configuration data for Audience core and webparts|
|237| [modulelicense](modulelicense.md) |Module licenses, belonging to one single owner|
|238| [licenseassoclink](licenseassoclink.md) |Link between ModuleLicense and Associate, for per-assoc licenses; this is how licenses are assigned/consumed|
|239| [licensesatllink](licensesatllink.md) |Link between License and Satellite, for per-database licenses|
|240| [productversion](productversion.md) |Version information for code modules. Owner + code module must be unique|
|241| [messagehandler](messagehandler.md) |Presence and heartbeat of a message handler, should be updated once a minute. Older records are stale|
|242| [message](message.md) |Definition of a message, corresponding to the header of a protocol|
|243| [batchtask](batchtask.md) |Batch task request details, corresponding to the message body of a batch request message|
|244| [batchtaskdefinition](batchtaskdefinition.md) |Batch task definitiopns, populated from the SuperOffice.CRM.BatchProcessing.BatchTask attribute|
|245| [tzlocation](tzlocation.md) |Time zone location|
|246| [tzstdrule](tzstdrule.md) |Time zone rule for standard time|
|247| [tzdstrule](tzdstrule.md) |Time zone rule for daylight saving time|
|248| [basetzlocation](basetzlocation.md) |Time zone location for the database (how tz-related datetimes should be stored in the database)|
|249| [webappusage](webappusage.md) |Usage statistics for web applications|
|250| [credentials](credentials.md) |Alternative credentials|
|251| [phoneformat](phoneformat.md) |Formatting information for telephone numbers|
|252| [trayapp](trayapp.md) |Tray application presence. SuperOffice CRM web extensions.|
|253| [registry](registry.md) |System settings|
|254| [session\_object](session\_object.md) |Generic session object, accessible from ejscript etc, typically xml or name=value syntax, may be stored over several rows if big|
|255| [config](config.md) |This table contains certain system-wide configuration values.|
|256| [ticket\_attachment](ticket\_attachment.md) |This table connects an attachment to a message. It references the entry in the attachment table, and the message.|
|257| [ej\_category](ej\_category.md) |This table contains categories, in which tickets are categorized. The categories are organized in a hierarchial manner.|
|258| [ej\_message](ej\_message.md) |This table contains the messages listed under tickets.|
|259| [message\_header](message\_header.md) |This table contains small pieces of information which is listed over the body for each message.|
|260| [message\_customers](message\_customers.md) |This table contains all cutomers who are involved in a message|
|261| [ticket\_status\_history](ticket\_status\_history.md) |This table contains the history of a tickets statuses. Each time a ticket changes status a copy of the previous status of the record will be saved |
|262| [ticket](ticket.md) |This table contains the tickets (requests) of the system. Its purpose should be evident.|
|263| [ticket\_status](ticket\_status.md) |This table user defined ticket status values.|
|264| [ticket\_customers](ticket\_customers.md) |This table allows several customers to be connected to several tickets (many-to-many)|
|265| [invoice](invoice.md) |This table contains invoice entries, normally created when an invoice is sent to a customer, and we want to update the balance.|
|266| [invoice\_sum](invoice\_sum.md) |This table is used temporarily when listing invoice statistics. It is used because we need to sort balances from both customers and companies.|
|267| [ticket\_log](ticket\_log.md) |This table contains log entries for the tickets.|
|268| [ticket\_log\_change](ticket\_log\_change.md) |This table contains log entries for the tickets.|
|269| [ticket\_log\_action](ticket\_log\_action.md) |This table contains actions for the tickets.|
|270| [category\_membership](category\_membership.md) |This table connects users to categories (many-to-many).|
|271| [mail\_in\_filter](mail\_in\_filter.md) |This table contains entries for the mailboxes the eJournal system is fetching mail from (POP3 or IMAP).|
|272| [mail\_in\_uidl](mail\_in\_uidl.md) |This table is used to avoid spamming the system by importing the same message several times (normally a result of a crash somewhere). When a mailbox is openede, then unique id for each message is stored in this table, and then removed only when the message has been correctly imported and deleted from mailbox.|
|273| [mail\_alias](mail\_alias.md) |This table contains the alias&amp;apos;es for each mailbox, one-to-many-relation. It is in so we can substract the alias&amp;apos;es when when listing the recipients of a message.     |
|274| [ticket\_alert](ticket\_alert.md) |This table will contain ticket escalation levels. A ticket will be escalated along a &amp;apos;chain&amp;apos; of these levels.|
|275| [ticket\_priority](ticket\_priority.md) |This table contains the ticket priorities.|
|276| [reply\_template\_folder](reply\_template\_folder.md) |This table contains entries for folders for reply templates.|
|277| [reply\_template](reply\_template.md) |Templates for automatic and manual replies to emails/sms organized hierachically|
|278| [reply\_template\_attachment](reply\_template\_attachment.md) |This table is used to connect attachments to reply templates (many-to-many).|
|279| [reply\_template\_body](reply\_template\_body.md) |Contains the body of the reply templates in different languages|
|280| [doc\_document](doc\_document.md) |This table contains documents.|
|281| [doc\_folder](doc\_folder.md) |A document folder.|
|282| [kb\_entry](kb\_entry.md) |This table contains FAQ entries.|
|283| [kb\_category](kb\_category.md) |Knowledge base folder hierarchy|
|284| [kb\_attachment](kb\_attachment.md) |This table connects FAQ entries to attachments.|
|285| [kb\_http\_link](kb\_http\_link.md) |This table contains URL&amp;apos;s associated with a single FAQ entry.|
|286| [kb\_group](kb\_group.md) |This table contains FAQ groups. A group is a cluster of entries (potentially located anywhere in the FAQ hierarchy). A group is located in a certain category.|
|287| [kb\_group\_entry](kb\_group\_entry.md) |This table contains group entries for FAQ groups.|
|288| [kb\_entry\_keyword](kb\_entry\_keyword.md) |This table contains all keywords for the faq entries|
|289| [kb\_entry\_comment](kb\_entry\_comment.md) |Comments to entries in the knowledge base, typically made by customers|
|290| [kb\_entry\_log](kb\_entry\_log.md) |Who and when, if somebody edits a knowledge base entry|
|291| [kb\_category\_log](kb\_category\_log.md) |Who and when, if somebody edits a knowledge base folder|
|292| [kb\_workflow](kb\_workflow.md) |Knowledge base workflow steps|
|293| [kb\_workflow\_access](kb\_workflow\_access.md) |Control of who can do what in a knowledge base workflow step|
|294| [kb\_solution\_finder](kb\_solution\_finder.md) |Knowledge base problem solving wizard, categories and subcategories for drilling down|
|295| [kb\_solution\_finder\_entry](kb\_solution\_finder\_entry.md) |Knowledge base problem solving wizard, items in a category linking to a knowledge base entry|
|296| [attachment](attachment.md) |This table contains metadata for attachments. The actual attachments are stored directly on disk, with filenames based on the the primary key for this table.|
|297| [login](login.md) |This table contains entries for the user sessions. |
|298| [login\_customer](login\_customer.md) |This table contains entries for customer sessions. At first only used for Soap logins, but will later also be used for web logins|
|299| [ejuser](ejuser.md) |This table contains entries for the users of the system.|
|300| [timestamps](timestamps.md) |Timestamp information|
|301| [notify](notify.md) |This table contains the pop-up messages displayed for users for various events, such as &amp;apos;new ticket&amp;apos;, etc.|
|302| [help](help.md) |This table contains the help pages.|
|303| [company\_domain](company\_domain.md) |This table contains web-domains associated with a certain cust_company entry.|
|304| [extra\_fields](extra\_fields.md) |This table contains entries for the extra fields in the system.|
|305| [extra\_tables](extra\_tables.md) |This table contains entries for the extra tables in the system.|
|306| [hierarchy](hierarchy.md) |This table contains folders used to group the extra tables in the system.|
|307| [extra\_menus](extra\_menus.md) |This table contains entries for the extra menus in the system.|
|308| [extra\_tables\_result](extra\_tables\_result.md) |Result set of executed search in ejournal extra tables|
|309| [extra\_tables\_entry](extra\_tables\_entry.md) |Hits/entries in result set of executed search in ejournal extra tables|
|310| [ms\_filter](ms\_filter.md) |This table contains email filters. These are the filters allowing you to do advanced parsing of incomming emails.|
|311| [ms\_filter\_mail](ms\_filter\_mail.md) |This table connects mail filters (ms_filter) to mailboxes (mail_in_filter).|
|312| [ms\_trashbin](ms\_trashbin.md) |This table contains entries for emails which have been trashed by a filter, waiting for confirmation of deletion or import.|
|313| [ms\_substitute](ms\_substitute.md) |Regexp for extracting info from emails when they enter they system|
|314| [eab\_folder](eab\_folder.md) |This table contains eab (email address book) folders, used for containing email addresses.|
|315| [eab\_entry](eab\_entry.md) |This table contains eab (email address book) entries, i.e. an alias (&amp;apos;Ola Hansen&amp;apos;) and an address (&amp;apos;ola@hansen.as&amp;apos;).|
|316| [mail\_block](mail\_block.md) |This table controls the spam-protection system, ensuring that a single email recipient does not recieve too many emails during a certain period of time.|
|317| [ext\_datasource](ext\_datasource.md) |This table contains external datasources, used for databaseintegration of customers and companies.|
|318| [ext\_table](ext\_table.md) |This table contains entries used for mapping an external table to an internal table (customer or cust_company) for database integration.|
|319| [ext\_field](ext\_field.md) |This table contains entries mapping an external field to an internal field. Used for database integration.|
|320| [cust\_lang](cust\_lang.md) |This table contains entries for customer languages.|
|321| [cust\_category](cust\_category.md) |This table contains entries for categories exposed through a customer language.|
|322| [password\_rules](password\_rules.md) |This table may contain one entry specifying rules for passwords.|
|323| [ej\_role](ej\_role.md) |Define access rights, memberships and other properties for role user members|
|324| [role\_member](role\_member.md) |Users linked to a role. Deprecated.|
|325| [role\_category](role\_category.md) |Category membership associated with a role|
|326| [role\_element](role\_element.md) |Profiles associated with a role|
|327| [role\_workflow](role\_workflow.md) |Knowledge base workflow access rights associated with a role|
|328| [element\_profile](element\_profile.md) |The new (4.0) profile table. Contains profile for a single Html-element. Connected through element_profile_link|
|329| [profile](profile.md) |Deprecated. This table contains entries for the user profiles.|
|330| [chat\_topic](chat\_topic.md) |This table contains chat topics.|
|331| [chat\_topic\_user](chat\_topic\_user.md) |This table connected the chat topics with the users (i.e. the membership).|
|332| [chat\_session](chat\_session.md) |This table contains chat sessions.|
|333| [chat\_message](chat\_message.md) |This table contains messages in a chat session.|
|334| [s\_shipment](s\_shipment.md) |Contains info about one shipment. The addresses are stored in s_shipment_addr|
|335| [s\_message](s\_message.md) |A message used in a shipment. Can be html and/or plain text|
|336| [s\_link](s\_link.md) |Links in messages to measure success rate of a campaign.|
|337| [s\_link\_customer](s\_link\_customer.md) |A connection between a customer and a link. Registered customers are identified when clicking on a link|
|338| [s\_link\_customer\_statical](s\_link\_customer\_statical.md) |A connection between a customer and a link. Registered customers are identified when clicking on a link|
|339| [s\_picture\_folder](s\_picture\_folder.md) |This table contains all picture folders|
|340| [s\_picture\_entry](s\_picture\_entry.md) |This table describes each picture in the database|
|341| [s\_washing](s\_washing.md) |Register of all bounced mail to enabel washing|
|342| [s\_bounce\_shipment](s\_bounce\_shipment.md) |Email bounces from customers|
|343| [s\_washing\_list](s\_washing\_list.md) |Unused table that is ment to be used for active washing in spm v2|
|344| [s\_list](s\_list.md) |A list, dynamic or static|
|345| [s\_list\_element](s\_list\_element.md) |Elements in a static list.|
|346| [s\_list\_customer](s\_list\_customer.md) |Elements in a customer list.|
|347| [s\_shipment\_addr](s\_shipment\_addr.md) |Addresses that are ready to be sent in a shipment.|
|348| [s\_list\_shipment](s\_list\_shipment.md) |A connector between shipment and list so that one shipment can have many lists, and one list can have many shipments|
|349| [s\_attachment](s\_attachment.md) |A connector between a message and attachments. One message can contain many attachments.|
|350| [s\_dyn\_criteria](s\_dyn\_criteria.md) |Contains criterias for a dynamic list.|
|351| [outbox](outbox.md) |Outgoing emails with sending status and other info|
|352| [inbox](inbox.md) |Info and status for safe email import|
|353| [legal\_html\_tags](legal\_html\_tags.md) |This table is used as a list of all legal HTML tags. HTML tags not in this list                  will be ignored when viewing html versions of messages|
|354| [kb\_entry\_words](kb\_entry\_words.md) |This table contains all the words and how many times the are refered                  to in the FAQ entires|
|355| [word\_relations](word\_relations.md) |This table shows which word are used in which FAQ entry, and how many times            they are used in each|
|356| [temporary\_words](temporary\_words.md) |This table is used as a temporary table, containing the words we want                  to search for in the FAQs|
|357| [wsdl\_description](wsdl\_description.md) |Soap wsdl files|
|358| [dictionary](dictionary.md) |User added dictionary words|
|359| [dictionary\_base](dictionary\_base.md) |Language catalog for the ejournal dictionaries (automatic proof reading of message text etc)|
|360| [invoice\_entry](invoice\_entry.md) |This table contain all invoices, connected to a message|
|361| [invoice\_type](invoice\_type.md) |A invoiceable item category (a product or service) that provides default invoice line values|
|362| [soap\_access](soap\_access.md) |Table that contains constraints on the access to the soap interface|
|363| [hotlist](hotlist.md) |The table is used by the hotlist to store the relationship between tickets and users|
|364| [log\_events](log\_events.md) |System log|
|365| [log\_debug](log\_debug.md) |A log used for debugging, especially useful for bLogic/ejscript|
|366| [form\_keys](form\_keys.md) |Keys that makes sure a form is not posted twice|
|367| [sms\_hysteria](sms\_hysteria.md) |Avoid sending too many sms messages in a short time interval to one person|
|368| [item\_config](item\_config.md) |This table is a generic table for storing item configuration. It is only used by the class ItemConfig.|
|369| [snapshot](snapshot.md) |Snapshots taken of the system database and attachments via soap|
|370| [screen\_definition](screen\_definition.md) |A configurable screen|
|371| [screen\_definition\_action](screen\_definition\_action.md) |An action to perform for a certain button in an screen|
|372| [screen\_definition\_element](screen\_definition\_element.md) |An element in a configurable screen|
|373| [screen\_definition\_hidden](screen\_definition\_hidden.md) |The name of a hidden variable to keep for this screen|
|374| [screen\_definition\_language](screen\_definition\_language.md) |Custom language variables used for screens|
|375| [screen\_chooser](screen\_chooser.md) |Screen choosers|
|376| [scheduled\_task](scheduled\_task.md) |A scheduled entry executing a script at certain times|
|377| [ejscript](ejscript.md) |ejscript|
|378| [system\_script](system\_script.md) |A table containing the system script|
|379| [schedule](schedule.md) |Generic scheduled tasked handling time scheduling, locking and error messages|
|380| [locking](locking.md) |Generic locking and error messages|
|381| [dbi\_agent](dbi\_agent.md) |DBI agent settings|
|382| [dbi\_agent\_field](dbi\_agent\_field.md) |DBI agent fields|
|383| [dbi\_agent\_schedule](dbi\_agent\_schedule.md) |DBI agent schedule settings|
|384| [ejpackage](ejpackage.md) |This table stores packages on the system.|
|385| [ejpackage\_item](ejpackage\_item.md) |This table stores info on installed packages in the system|
|386| [message\_id](message\_id.md) |This table links an email message id to an eJournal item|
|387| [ejscript\_debug](ejscript\_debug.md) |This table contains information when debugging an ejscript|
|388| [sms](sms.md) |This table will hold outgoing sms messages when transmitted with WebServices|
|389| [user\_candidate](user\_candidate.md) |This table will hold user candidate secrets|
|390| [s\_smtp\_servers](s\_smtp\_servers.md) |Contains the smtp server for a shipment|
|391| [ejselection](ejselection.md) |This table stores selections, dynamic groups.|
|392| [ejsel\_ejsel](ejsel\_ejsel.md) |This table defines sources for complex selections in a many/many relationship|
|393| [ejsel\_source\_idlist](ejsel\_source\_idlist.md) |This table stores id list source for selections|
|394| [ejsel\_source\_script](ejsel\_source\_script.md) |This table stores a selection script source|
|395| [ejsel\_source\_xml](ejsel\_source\_xml.md) |This table stores a selection source as xml|
|396| [static\_list\_ref](static\_list\_ref.md) |This table stores id references for selections id lists|
|397| [ejsel\_meta\_result](ejsel\_meta\_result.md) |This table stores result meta data|
|398| [ejsel\_result\_set](ejsel\_result\_set.md) |This table stores result set reference data, result sets for selections|
|399| [tree\_explorer\_entry](tree\_explorer\_entry.md) |This table stores the entries in a tree-explorer|
|400| [tree\_explorer\_link](tree\_explorer\_link.md) |This table stores the link of entries in a tree-explorer|
|401| [external\_document](external\_document.md) |This table stores documents which can be viewed externaly, through the customer module|
|402| [autosave](autosave.md) |Autosaved text clobs from ejscript and emarketeer messages|
|403| [user\_attribute](user\_attribute.md) |This table is used for storing various attributes for users.|
|404| [notice\_frame](notice\_frame.md) |PID controller for automatic adjustment of pop up message check rate|
|405| [s\_sent\_message](s\_sent\_message.md) |Emarketeer message control|
|406| [access\_script](access\_script.md) |Scripts to implement row-based access rules (sentry light)|
|407| [outgoing\_message](outgoing\_message.md) |Delivery of outgoing messages to messageplugins, updated with status asynchroneously|
|408| [productcategory](productcategory.md) |List for the ProductCategory field of the Product table (Quote Management)|
|409| [productcategorygrouplink](productcategorygrouplink.md) |User group link table for ProductCategory, for MDO item hiding|
|410| [productcategoryheadinglink](productcategoryheadinglink.md) |Heading link table for ProductCategory, for MDO item headings|
|411| [productfamily](productfamily.md) |List for the ProductFamily field of the Product table (Quote Management)|
|412| [productfamilygrouplink](productfamilygrouplink.md) |User group link table for ProductFamily, for MDO item hiding|
|413| [productfamilyheadinglink](productfamilyheadinglink.md) |Heading link table for ProductFamily, for MDO item headings|
|414| [producttype](producttype.md) |List for the ProductType field of the Product table (Quote Management)|
|415| [producttypegrouplink](producttypegrouplink.md) |User group link table for ProductType, for MDO item hiding|
|416| [producttypeheadinglink](producttypeheadinglink.md) |Heading link table for ProductType, for MDO item headings|
|417| [erpconnector](erpconnector.md) |One ERP Connector, known by its URL|
|418| [erpconnection](erpconnection.md) |One connection to an ERP connector, specifying Client and other required information|
|419| [erpconnectionactortype](erpconnectionactortype.md) |Data about the configuration of one Erp Actor on one ErpConnection|
|420| [erpconnectionaccess](erpconnectionaccess.md) |Access control for Erp Connections|
|421| [connectionconfigfield](connectionconfigfield.md) |Configuration data for Erp and Quote Connections|
|422| [erpinternalkey](erpinternalkey.md) |The internal (superoffice-facing) key related to a synchronized record|
|423| [erpexternalkey](erpexternalkey.md) |The external (ERP-facing) key related to a synchronized record / connection|
|424| [erplistitemmapping](erplistitemmapping.md) |Defines a mapping of ERP to CRM fields, per connection and actor type|
|425| [erpfield](erpfield.md) |Store the metadata describing the fields that belong to an actor/connection combination, as described by the Erp Connector|
|426| [erpsynclog](erpsynclog.md) |Record all field changes done by the Erp Sync|
|427| [paymentterms](paymentterms.md) |The list of payment terms, in the internal product register|
|428| [paymenttermsgrouplink](paymenttermsgrouplink.md) |User group link table for PaymentTerms, for MDO item hiding|
|429| [paymenttermsheadinglink](paymenttermsheadinglink.md) |Heading link table for PaymentTerms, for MDO item headings|
|430| [paymenttype](paymenttype.md) |The list of payment types, in the internal product register|
|431| [paymenttypegrouplink](paymenttypegrouplink.md) |User group link table for PaymentType, for MDO item hiding|
|432| [paymenttypeheadinglink](paymenttypeheadinglink.md) |Heading link table for PaymentType, for MDO item headings|
|433| [deliveryterms](deliveryterms.md) |The list of Delivery terms, in the internal product register|
|434| [deliverytermsgrouplink](deliverytermsgrouplink.md) |User group link table for DeliveryTerms, for MDO item hiding|
|435| [deliverytermsheadinglink](deliverytermsheadinglink.md) |Heading link table for DeliveryTerms, for MDO item headings|
|436| [deliverytype](deliverytype.md) |The list of Delivery types, in the internal product register|
|437| [deliverytypegrouplink](deliverytypegrouplink.md) |User group link table for DeliveryType, for MDO item hiding|
|438| [deliverytypeheadinglink](deliverytypeheadinglink.md) |Heading link table for DeliveryType, for MDO item headings|
|439| [priceunit](priceunit.md) |The list of price units, in the internal product register (meter, ton, bushel, microsecond, gradus, τρυβλίον, 五合枡, دونم or whatever)|
|440| [priceunitgrouplink](priceunitgrouplink.md) |User group link table for PriceUnit, for MDO item hiding|
|441| [priceunitheadinglink](priceunitheadinglink.md) |Heading link table for PriceUnit, for MDO item headings|
|442| [subscriptionunit](subscriptionunit.md) |The list of Subscription units, in the internal product register (year/quarter/month etc., or perhaps amounts if volume-based subscription)|
|443| [subscriptionunitgrouplink](subscriptionunitgrouplink.md) |User group link table for SubscriptionUnit, for MDO item hiding|
|444| [subscriptionunitheadinglink](subscriptionunitheadinglink.md) |Heading link table for SubscriptionUnit, for MDO item headings|
|445| [quotelineconfiguration](quotelineconfiguration.md) |Configuration of quote lines - which fields are in use, rights, labels etc|
|446| [saletypequoteattachment](saletypequoteattachment.md) |Default attachments to quotes linked to sales of this type|
|447| [quoteversionattachment](quoteversionattachment.md) |Actual attachments to a quote|
|448| [resourceoverride](resourceoverride.md) |Generic mechanism for overriding (or even defining new) text resources, in multiple languages|
|449| [erpconfiguration](erpconfiguration.md) |Global settings for the Erp Integration Server|
|450| [ejcategorygrouplink](ejcategorygrouplink.md) |User group link table for EjCategory, for mass handling ej_category members|
|451| [ticket\_type](ticket\_type.md) |Contains ticket types, used to drive processing logic together with ticket relations|
|452| [ticket\_relation\_type](ticket\_relation\_type.md) |Contains ticket relation types, used to drive processing logic together with ticket relations|
|453| [ticket\_relation\_action](ticket\_relation\_action.md) |Contains ticket relation actions, used to drive processing logic together with ticket relations|
|454| [ticket\_relation](ticket\_relation.md) |Contains ticket relations, used to drive processing logic|
|455| [favourite](favourite.md) |Favourite records (star-marking)|
|456| [databasemodel](databasemodel.md) |New DatabaseModel used by Continuous Database|
|458| [saintconfiguration](saintconfiguration.md) |Configuration information for the Saint system|
|459| [tags](tags.md) |MDO List of tags for Service entities|
|460| [tagsgrouplink](tagsgrouplink.md) |User group link table for Tags, for MDO item hiding|
|461| [tagsheadinglink](tagsheadinglink.md) |Heading link table for Source, for MDO headers|
|462| [quick\_reply](quick\_reply.md) |Personal quick reply text fragments|
|463| [consentpurpose](consentpurpose.md) |GDPR purpose alternatives|
|464| [legalbase](legalbase.md) |Legal base for GDPR (Article 6)|
|465| [consentsource](consentsource.md) |Consent source for GDPR|
|466| [consentperson](consentperson.md) |Link table that defines who has which consents|
|467| [categoryfamily](categoryfamily.md) |Grouping table so that multiple company categories can be grouped under one term; to simplify searching for things like &apos;all customers&apos;|
|468| [script\_trace](script\_trace.md) |Scripts which should be traced|
|469| [script\_trace\_run](script\_trace\_run.md) |Traces of executed scripts|
|470| [attachment\_location](attachment\_location.md) |A location for storing attachments|
|471| [cust\_config](cust\_config.md) |This table contains JSON structures used for customizing the customer center|
|472| [form](form.md) |A form which can be published on a webpage and submitted by visitors|
|473| [form\_submission](form\_submission.md) |A form submission|
|474| [email\_account](email\_account.md) |Email account information|
|475| [email\_folder](email\_folder.md) |Corresponds to an email folder on a mail server|
|476| [service\_auth](service\_auth.md) |Authentication for a service (imap, smtp...)|
|477| [email\_item](email\_item.md) |Email data|
|478| [email\_attachment](email\_attachment.md) |Attachment info related to an email_item|
|479| [invitation](invitation.md) |Invitations to events|
|480| [s\_messageblock](s\_messageblock.md) |Contains a block of a mailing message, that can be reused in a mailing|
|481| [typicalsearch](typicalsearch.md) |Owner of a set of predefined selection criteria|
|482| [onlineapp](onlineapp.md) |Echo and track information about Online Apps and their usage|
|483| [pushnotificationservice](pushnotificationservice.md) |Used for storing handles to user devices that should receive push notifications|
|484| [shipmenttype](shipmenttype.md) |Shipment type list table. Classification of a mailing, allowing recipients to subscribe to lists|
|485| [shipmenttypereservation](shipmenttypereservation.md) |ShipmentTypes a person has reserved against. Note that the absense of a record here implies acceptance of a mailings of this type|
|486| [temporarykey](temporarykey.md) |Temporary keys for lightweight authentications such as changing ones subscriptions|
|487| [webhook](webhook.md) |Webhook URL to call when events occur in the client or in NetServer. Also tracks call+error statistics.|
|488| [associatehistory](associatehistory.md) |Historical information about associates that have been deleted. Most references are NOT declared as foreign keys; this is a historical table that should not be updated when further changes occur in the database|
