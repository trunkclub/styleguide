# Trunk Club iOS Typography Guide

## Text Styles

 Bold Text Styles | Font      | Size    | Color         | Uppercase
:-----------------|:---------:|:-------:|:-------------:| ---------:
 boldTextStyle    | Bold      | 12.0    | Primary       | Yes
 boldSelectedTextStyle | Bold | 14.0    | Secondary     | Yes
 boldDisabledTextStyle | Bold | 14.0    | Secondary     | Yes
 boldTitleTextStyle | Bold    | 16.0    | Primary       | Yes
 boldParagraphTextStyle | Bold | 16.0    | Primary       | No

 Serif Text Styles | Font      | Size    | Color         | Uppercase
:------------------|:---------:|:-------:|:-------------:|:---------:
 serifTextStyle    | Serif      | 16.0    | Primary       | No
 serifParagraphTextStyle | Serif | 20.0    | Primary       | Yes
 secondarySerifParagraphTextStyle | Serif | 14.0    | Secondary     | No
 serifHeaderTextStyle | Serif | 24.0    | Primary     | No

  Italic Text Styles | Font      | Size    | Color         | Uppercase
 :-------------------|:---------:|:-------:|:-------------:|:---------:
  italicTextStyle    | Italic      | 14.0    | Primary       | No

 Regular Text Styles | Font      | Size    | Color         | Uppercase
:-----------------|:---------:|:-------:|:-------------:|:---------:
 regularTextStyle | Regular      | 16.0    | Primary       | No
 regularParagraphTextStyle | Regular | 14.0    | Primary     | No
 regularPlaceholderTextStyle | Regular | 16.0    | Placeholder     | No
 regularAccentTextStyle | Regular    | 16.0    | Accent       | No
 secondaryTextStyle | Regular | 14.0    | Secondary       | No
 regularSelectedTextStyle | Regular | 16.0    | Secondary     | No
 regularDisabledTextStyle | Regular | 16.0    | Secondary     | No
 tableViewHeaderTextStyle | Regular | 11.0    | tableViewHeaderColor     | Yes

 Light Text Styles | Font      | Size    | Color         | Uppercase
:------------------|:---------:|:-------:|:-------------:|:---------:
 lightTextStyle    | Light      | 16.0    | Primary       | No
 lightParagraphTextStyle | Light | 14.0    | Primary       | No
 lightPlaceholderStyle | Light | 16.0    | Secondary     | No
 lightSubtitleStyle | Light | 12.0    | Secondary     | No

## Labels

 Label            | Text Style      
:-----------------|:---------:
 TCBoldLabel      | boldTextStyle      
 TCBoldParagraphLabel | boldParagraphTextStyle
 TCRegularPlaceholderLabel | regularPlaceholderTextStyle
 TCRegularParagraphLabel | regularParagraphTextStyle    
 TCSecondaryLabel | secondaryTextStyle
 TCLightLabel     | lightTextStyle      
 TCLightSubtitleLabel | lightSubtitleTextStyle
 TCLightParagraphLabel | lightParagraphTextStyle
 TCTableViewHeaderLabel | tableViewHeaderTextStyle    

## Table Views

### Table View Headers

#### MemberProfileHeaderView - Stylist App

 Element     | Style     
:------------|:----------------
  avatar     | --
  nameLabel | serifHeaderTextStyle
  emailLabel | TCLightSubtitleLabel
  locationLabel  | TCLightSubtitleLabel
  arrowImageView | --
  transactionLabel | TCLightParagraphLabel
  spendLabel | TCLightParagraphLabel
  creditsLabel | TCLightParagraphLabel
  transactionTitleLabel | TCTableViewHeaderLabel
  spendTitleLabel | TCTableViewHeaderLabel
  creditsTitleLabel | TCTableViewHeaderLabel

#### StylistHeaderView - Stylist App

 Element     | Style     
:------------|:----------------
 avatar     | --
 nameLabel | serifParagraphTextStyle
 emailLabel | TCLightSubtitleLabel

#### MeHeaderView - Member App

  Element     | Style     
 :------------|:----------------
  avatar     | --
  nameLabel | serif, 22.0, blackColor, false
  infoLabel | regularDisabledTextStyle
  arrowImageView | --

### Table View Cells

 Element     | Style     
:------------|:----------------
 textField   | regularTextStyle, lightPlaceholderStyle
 subtitleLabel | regularSelectedTextStyle
 detailLabel | TCLabel
 errorLabel  | regularFontWithSize:12.0, errorColor, no
 secondaryLabel | TCLightLabel
 accessoryImageView | --
 leftImageView | --
 rightButton | --
