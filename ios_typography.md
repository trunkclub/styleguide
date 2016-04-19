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

### TCTableViewCell

 Element     | Style     
:------------|:----------------
 textField   | regularTextStyle, lightPlaceholderStyle
 subtitleLabel | regularSelectedTextStyle
 detailLabel | TCLabel
 errorLabel  | regular, 12.0, errorColor, no
 secondaryLabel | TCLightLabel
 accessoryImageView | --
 leftImageView | --
 rightButton | --

### TCTableViewCell Subclasses

#### MemberProfileTableViewCell - Stylist App

Element     | Style     
:------------|:----------------
textField   | boldTextStyle, .Center
separatorView | --

#### MeViewController - Member App

Element     | Style     
:------------|:----------------
textField   | boldTextStyle, .Center
separatorView | --

#### ConversationCell - Stylist App

 Element     | Style     
:------------|:----------------
 memberAvatar   | --
 memberNameLabel | TCBoldParagraphLabel
 messageLabel | TCLightLabel
 timeLabel  | TCLightSubtitleLabel
 newMessageIndicator | --

#### MemberDetailNotesCell - Stylist App

  Element     | Style     
 :------------|:----------------
  headerLabel   | TCLabel
  noteLabel | TCLightLabel
  dateLabel | TCLightSubtitleLabel

#### WardrobeItemCell - Stylist App

   Element     | Style     
  :------------|:----------------
   itemImage   | --
   feedbackImage | --
   itemNameLabel | mono, 11.0, primary, false
   itemBrandLabel  | bold, 12.0, primary, false
   itemDetailsLabel | mono, 11.0, secondary, false

#### PreferenceTableViewCell - Member App

 Element     | Style     
:------------|:----------------
preferenceImageView   | --
preferenceTitleLabel | regular, 24.0, primary, false
preferenceSubtitleLabel | regular, 11.0, primary, true

### TCCollectionViewCell Subclasses

#### MenuItemCollectionCell - Stylist App

 Element     | Style     
:------------|:----------------
 imageView   | --
 titleLabel | TCLightParagraphLabel

#### ItemBasicsCell - Stylist App

  Element     | Style     
 :------------|:----------------
  itemImageView   | --
  titleLabel  | TCBoldLabel
  subtitleLabel | TCLabel
  descriptionLabel | mono, 14.0, primary, false
  pillLabel   | bold, 10.0, secondary, true
  pillView    | --

#### ItemBasicsCell - Member App

  Element     | Style     
 :------------|:----------------
  itemImageView   | --
  titleLabel  | primaryBoldTextStyle
  subtitleLabel | regularTextStyle
  descriptionLabel | secondaryTextStyle
  wardrobeLabel   | bold, 10.0, white, true

#### ItemFeedbackCell - Stylist App

   Element     | Style     
  :------------|:----------------
   memberAvatarImageView   | --
   headerLabel  | TCBoldLabel
   feedbackQuote | serifTextStyle
   pillLabel   | bold, 10.0, secondary, true
   pillView    | --

#### ItemHeaderCollectionCell - Member App

  Element     | Style     
 :------------|:----------------
  vendorLabel   | primaryBoldTextStyle
  descriptionLabel  | secondarySerifParagraphTextStyle
  pillView    | --

#### ItemOutfitCollectionCell - Member App

  Element     | Style     
 :------------|:----------------
  countLabel   | regular, 13.0, primary, false
  descriptionLabel  | bold, 16.0, secondary, false

#### ItemOutfitsCollectionCell - Member App

  Element     | Style     
 :------------|:----------------
  headerLabel   | bold, 14.0, primary, true

#### SearchCell - Stylist App

    Element     | Style     
   :------------|:----------------
    imageView   | --
    brandLabel  | TCLabel
    priceLabel | TCLabel

#### ContentInfoCell - Member App

   Element     | Style     
  :------------|:----------------
    titleLabel | serif, 24.0, primary, false
    descriptionLabel | TCLabel

#### ContentInfoCell - Member App

   Element     | Style     
  :------------|:----------------
    titleLabel | serif, 24.0, primary, false
    descriptionLabel | regularTextStyle

#### ContentInfoCell - Member App

   Element     | Style     
  :------------|:----------------
    textLabel  | secondaryTextStyle

#### MessageActionCell - Member App

   Element     | Style     
  :------------|:----------------
   titleLabel  | serifParagraphTextStyle
   stylistImageView  | --
   messageButton  | TCButton
   separatorView  | --

#### RecommendItemCell - Member App

  Element     | Style     
 :------------|:----------------
   imageView  | --
   brandLabel  | bold, 14.0, primary, false
   priceLabel  | secondaryTextStyle
   itemDetailsView  | --
   reservedView  | --
   reservedLabel  | regular, 12.0, secondary, true

#### RecommendedItemsGroupCell - Member App

   Element     | Style     
  :------------|:----------------
   titleLabel  | secondaryTextStyle

#### TCTrunkCell - Member App

  Element     | Style     
  :------------|:----------------
   imageView  | --
   brandLabel  | bold, 14.0, primary, false
   productNameLabel | regular, 14.0, primary, false
   priceLabel  | secondaryTextStyle
   removeTrunkLabel | bold, 13.0, error, false
   actionButton  | TCActionButton
   outfitsLabel  | secondaryTextStyle
   accessoryView  | --
