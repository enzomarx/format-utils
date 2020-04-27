# Format Utilities

## Introduction

Utilities for validating various formats of Indian system codes like Mobile, PAN, AADHAR, UID and more!

## Installation

```js
npm install format-utils --save
```

## Usage

```js
const { Validator } = require('format-utils');
```
OR
```js
import { Validator } from 'format-utils';
```

## Available Validators

### Mobile

A mobile is a 10 digit numerical code starting with either 6, 7, 8, 9.

```js
let isValid = Validator.mobile('9876543210');
// isValid = true

isValid = Validator.mobile('5678943210');
// isValid = false
```

### PIN (Postal Index Number)

A pincode is a 6 digit numeric code used by Indian Post.

#### Format
* The first character is a number from `1` to `9`.
* The second to sixth characters are numberical sequence from `00000` to `99999`.

```js
let isValid = Validator.pincode('400001');
// isValid = true

isValid = Validator.pincode('0123456');
// isValid = false
```

### PAN (Permanent Account Number)

A PAN is a 10 digit alphanumeric code issued by Income Tax Department of India.

#### Format
* The first three characters are alphabetic series running from `AAA` to `ZZZ`.
* The fourth character represents the status of the PAN holder.
  * `P` stands for Individual
  * `C` stands for Company
  * `H` stands for Hindu Undivided Family (HUF)
  * `A` stands for Association of Persons (AOP)
  * `B` stands for Body of Individuals (BOI)
  * `G` stands for Government Agency
  * `J` stands for Artificial Juridical Person
  * `L` stands for Local Authority
  * `F` stands for Firm/ Limited Liability Partnership
  * `T` stands for Trust
* The fifth character represents the first character of the PAN holder's last name/surname in case of an individual. In case of non-individual PAN holders fifth character represents the first character of PAN holder's name.
* The sixth to ninth characters are sequential numbers running from `0001` to `9999`.
* The tenth character is an alphabetic check digit.

Visit [this](https://www.incometaxindia.gov.in/Forms/tps/1.Permanent%20Account%20Number%20(PAN).pdf) to know more about PAN.

```js
let isValid = Validator.pan('ALWPG5809L');
// isValid = true

isValid = Validator.pan('ABAB12345Y');
// isValid = false
```

### TAN (Tax Deduction and Collection Account Number)

A TAN is a 10 digit alphanumeric code.

#### Format
* The first four characters are alphabetic series running from `AAAA` to `ZZZZ`.
* The fifth to ninth characters are sequential numbers running from `00001` to `99999`.
* The tenth character is an alphabetic character.

```js
let isValid = Validator.tan('RAJA99999B');
// isValid = true

isValid = Validator.tan('RAJA999991');
// isValid = false
```

### UAN (Universal Account Number)

A UAN is a 12 digit numberic code that is issued to member of the Employees’ Provident Fund Organisation (EPFO).

```js
let isValid = Validator.uan('987654321098');
// isValid = true

isValid = Validator.uan('A98765432109');
// isValid = false
```

### IFSC (Indian Financial System Code)

A IFSC is a 11 digit alphanumberic code that is issued to member of the Employees’ Provident Fund Organisation (EPFO).

#### Format
* The first four characters are alphabets that denote the bank name.
* The fifth character is numerical zero (`0`).
* The sixth to eleventh characters are numerical code that denote the branch name.


```js
let isValid = Validator.ifsc('SBIN0011569');
// isValid = true

isValid = Validator.ifsc('BK1D0006046');
// isValid = false
```

### ESIC (Employee State Insurance Corporation) Code

A ESIC code is a 17 digit numerical code that is issued by Employee State Insurance Corporation.

```js
let isValid = Validator.esic('12345678901234567');
// isValid = true

isValid = Validator.esic('1234567890123456');
// isValid = false
```

### IMEI (International Mobile Equipment Identity)

A IMEI is a 15 digit numeric code to identify mobile phones, as well as some satellite phones.
The last digit of IMEI is a Luhn check digit.

```js
let isValid = Validator.imei('490154203237518');
// isValid = true

isValid = Validator.imei('490154203237519');
// isValid = false
```

### AADHAAR

Aadhaar is a 12 digit numberic code that can be obtained by residents or passport holders of India, based on their biometric and demographic data.

#### Format
* The first character is a number between `2` and `9`.
* The second to eleventh characters are random numbers.
* The twelfth character is a Verhoeff check digit.

```js
let isValid = Validator.aadhaar('234567890124');
// isValid = true

isValid = Validator.aadhaar('187654321096');
// isValid = false
```

### AADHAAR VID (Aadhaar Virtual ID)

Aadhaar VID is a 16 digit numberic code that can be used instead of Aadhaar number at the time of authentication to avoid sharing of Aadhaar number.
The last digit is a Verhoeff check digit.

```js
let isValid = Validator.aadhaarVID('9876543210987659');
// isValid = true

isValid = Validator.aadhaarVID('6234897234982734');
// isValid = false
```

### GSTIN (Goods & Services Tax Identification Number)

A GISTIN is a 15 digit alphanumeric code assigned to a business or person registered under the GST Act.

#### Format
* The first two characters are numerical series from `01` to `37` denoting state code.
* The third to twelfth characters are [PAN](#pan-permanent-account-number) number of the GST registered entity.
* The thirteenth character is a alphabet assigned based on the number of registration within a state.
* The fourteenth character is `Z` by default.
* The fifteenth character is a check codeand can be an alphabet or a number.

```js
let isValid = Validator.gst('22ALJPT5243L1ZS');
// isValid = true

isValid = Validator.gst('22ALJPT5243L1ZB');
// isValid = false
```

### Vehicle Registration (Number Plate)

A vehicle number plate is an alphanumeric code assigned to a vehicle registered in India.

The current format of the registration index consists of 4 parts.

#### Format
* The first two characters are alphanumeric code of the State / Union Territory where the vehicle is registered.
* The third & fourth characters the sequential number of a district.
* The third part consists of one, two or three letters or no letters at all.
* The fourth part is a number from 1 to 9999, unique to each plate.

```js
let isValid = Validator.vehicleRegistration('DL4CAF4943');
// isValid = true

isValid = Validator.vehicleRegistration('DL4CAF494G');
// isValid = false
```
