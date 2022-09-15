# Customization Standards Guidelines

- <a href="#eliminate-customization">**Eliminate Customization**</a>
- <a href="#customization-by-modification">**Customization By Extension**</a>
- <a href="#customization-by-extension">**Customization by Modification**</a>

<br>

## Eliminate Customization
Void customization as you can!; you can eliminate the need for customization by altering the application configuration (such as setting up a descriptive flexfield).

<br>

## Customization by Modification
-  When you cannot meet a requirement using Oracle Application features and customization by extension is not an option, you can use customization by modification.
-  You must copy the component to be modified into a custom application and follow the guidelines for customization by extension.
-  If you cannot define the modified component in a custom application, you should preserve a copy of the original.
- Customization by extension are not supported by Oracle Support Services, nor the Applications Division.

<br>

> **Oracle Recommend!** 
> > You should eliminate any customization by modification.

<br>

## Customization By Extension

- You separate your application extensions from Oracle Applications components for easy identification and to reduce the risk of loss during an upgrade or patch.
- To keep new components separate, you **implement a custom application** and make it the owner of the new components.
- It would be best if you customized by extension rather than by modification to void the risk of overwriting or losing your customization during an upgrade or patch.

<br>

### Implement Custom Application

- You may implement one custom application that owns all custom components or many custom applications that own custom components.
- The short name can be up to 50 characters, but Oracle recommends using only three to five for ease in maintaining your application and calling routines that use your short name.
- The application’s short name should NOT start with ”O”, “CP”, and “E”, as well as all names currently used in Oracle Applications products.
- Oracle recommends that your custom application short name begins with “XX”.

#### Example

| Attribute | Value |
| :-  | :---- |
| Short Name | XXD |
| Application Name | Demasy Custom Applications |

<br>

> **Demasy Recommend!** 
> > I recommend implementing a single custom application called “xxd” than owns all the custom components, including all database objects, and applications components.

