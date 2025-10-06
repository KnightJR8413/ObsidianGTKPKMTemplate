---
name: <%* let name = await tp.system.prompt("Name") %> <% name %>
birthday:
nicknames:
gender:
height:
relation:
tags:
type: person
relatedto:
---
<%* 
const nameArray = name.split(" ");
let filename = "/" + nameArray[0];
const nameArrLen = nameArray.length;
if ( nameArrLen > 1 ) {
	filename += " ";
	filename += nameArray[nameArrLen - 1];
}
tp.file.move( tp.file.folder( true ) + filename ); 
if(false){ _%>
#template 
<%* } _%>

## Notes


## Gift List ideas