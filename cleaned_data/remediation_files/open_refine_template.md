# Open Refine Template University of Tennessee Handbooks


## Template

#### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```
####Body

```
<mods>
<identifier type="local">{{cells["Identifier"].value}}</identifier>

<titleInfo supplied="yes"><title>{{cells['title'].value}}</title></titleInfo>

{{if(isBlank(cells['title_alternative'].value), '', '<titleInfo><title>' + cells["title_alternative"].value + '</title></titleInfo>')}} 

{{if(isBlank(cells['date'].value), '', '<originInfo><dateIssued>' + cells['date'].value + '</dateIssued><dateIssued encoding="edtf">' + cells['date'].value + '</dateIssued>' + if(isBlank(cells['Publisher'].value), '', '<publisher>' + cells['Publisher'].value + '</publisher><place><placeTerm valueURI="http://id.loc.gov/authorities/names/n79109786">Knoxville (Tenn.)</placeTerm></place>') + '</originInfo>')}}

<abstract>{{cells["Abstract"].value}}</abstract>

<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form>
{{if(isBlank(cells['form2'].value), '', '<form authority="aat" valueURI="' + cells['form2_URI'].value + '">' + cells['form2'].value + '</form>')}}
{{if(isBlank(cells['form3'].value), '', '<form authority="aat" valueURI="' + cells['form3_URI'].value + '">' + cells['form3'].value + '</form>')}}
<extent>{{cells["Extent"].value}}</extent></physicalDescription>

{{if(isBlank(cells['subject'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_URI'].value + '"><topic>' + cells['subject'].value + '</topic></subject>')}}

{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}

{{if(isBlank(cells['subject3'].value), '', '<subject authority="naf" valueURI="' + cells['subject3_URI'].value + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}


<typeOfResource>{{cells['typeOfResource'].value}}</typeOfResource>

<language><languageTerm authority="iso639-2b" type="text">English</languageTerm></language>

<classification authority="lcc">{{cells['Call number'].value}}</classification>

<relatedItem displayLabel="Project" type="host"><titleInfo><title>University of Tennessee Student Handbook</title></titleInfo></relatedItem>

<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation></location>

<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource></recordInfo>

<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>

```

#### Suffix

```
</modsCollection>
```