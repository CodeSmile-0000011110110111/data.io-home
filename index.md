---
layout: post
title: Got data?
---

# Use data&lt;io&gt; !

C#. Clean. Correct. Fast. Flexible. Modular. Tested. Unity.

SQL. GSheets. SODB. CSV. JSON. SQLite(r). More in progress ...

Served on the side (I just can't *NOT* code things the right way):
* ScriptBuilder => fully customizable C# script generator with type descriptions so you only need to fill in names and method bodies
* Auto-Generate => Classes to DB schema *AND* DB schema or CSV to classes.
* SQLBuilder => type-safe, quote-escaped SQL query builder (which will eventually understand various dialects, too)
* Memory-Cached ScriptableObject Database (SODB) => serializable to JSON if needed
* No-Reflection SQLite => ´IList<IList<object>> rowsWithValues = SQLite*r*Command.Query("Select * FROM MyTable");´
* Fast Type/Value conversion from strings, with support for culture-specific number formats and any text encoding.
* Custom Editor tools fully supported with Inspector-ready settings. Build your own toolchain easily.
* Full source code included. Nothing is purposefully hidden! With JetBrains Code annotations.
* Documented use of external code/libs and their licenses.
* Latest libs included for convenience. Currently that's SQLite, Google Sheets API.

Supports any workflow: 
* (turn Code into Data) <=> (turn Data into Code)
* (Let me handle it) <=> (Wow, it just works)
* (SQL Lover) <=> (No SQL, please!)

  
  ...
  ...
  ...
  
## (below is first draft)

data.io makes it irrelevant WHERE or HOW your custom (game) data is stored. Sync data to one or another representation (Database, Spreadsheet, ScriptableObject, C# code) as needed. Even on a "per build", "per platform" or "editor vs runtime" basis. It let's you choose how you want to work with data, with which tools (Databases, Spreadsheets, C# IDE, Unity Inspector, custom ..) and how to store data (SQL, CSV, JSON, custom ..) and to enable that, there's only very few conventions to follow that are best practice anyway. 

<a href="https://github.com/sitterheim/data.io-home/wiki">Learn more in the wiki</a>.

data.io is coming Summer/Autumn 2022 to the Unity Asset Store!

Current focus is to transform SQL (specifically: SQLite) databases by
- generating C# code from the database schema and properly resolving relations, or
- generating a database schema from C# code without requiring attributes, and by
- having an in-memory representation of the data in a ScriptableObject Database (SODB)

The golden rule here is "convention over configuration" borrowed from the <a href="https://rubyonrails.org/doctrine#:~:text=such%20going%20forward.-,Convention%20over%20Configuration,in%20areas%20that%20really%20matter.">Ruby on Rails project</a>.

Additional features:
- Data Import/Export
  - SQLite <=> SODB <=> CSV <=> JSON <=> C# ScriptBuilder
  - Automatic: change or add a file to your project and the workflow ScriptableObject knows what to do with it (ie import into SQL, generate scripts, etc)
  - CSV Reader: fully-featured, lightweight, configurable (ie delimiter, text encoding, number & currency formats, data-implied System.Type conversion, relations, ...)
- SODB: ScriptableObject database
  - No SQL needed, LINQ available
  - statically typed access to your data
  - in-memory representation of your database (<a href="https://www.youtube.com/watch?v=KUjeQDZ4P9M">watch this video</a> to learn why this is a good thing!)
  - automatic resolution of relationships => AutorId column replaced by reference to Author class or List<Author>
  - serializable to JSON, for devices where SQLite is problematic & where performance matters (iOS, Android, UWP, WebGL)
  - editable in Unity Inspector GUI (in consideration: Odin Inspector support)
- C# ScriptBuilder
  - can be used for any script generating purpose with a simple API
  - also generates Assembly Definition files
- More ...
  - Interested? Contact me! => fremdspielen (at) gmail.com
  - I'm looking for: early adopters, real-world datasets for testing, understanding of how you work with data, with which tools, what pains you the most, etc.
