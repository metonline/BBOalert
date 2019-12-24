# BBOalert

Automatic alert in Bridge Base Online service (www.bridgebase.com)

We assume that you are familiar with BBO.

## Purpose

During the bidding, conventional calls must be alerted and explained to the opponents. Playing artificial bidding systems on BBO is not practical because explaining each alerted call is time consuming and therefore frustrating for all participants. As SAYC is standard within BBO community, practicing other 'natural' bidding system like French Standard or Acol will require frequent alerting too.

BBOalert resolves this problem. Artificial bidding sequences can be predefined in a table. Opponents get the explanation automatically and immediately. Explanations entered manually during the game are recorded for future use.

BBOalert has similar functionallity as "Full Disclosure" which is no longer supported by BBO. Certain features of "Full Disclusure" have not been implemented yet (e.g. seat sensitive openings) and will be perhaps added as needed by the community. One difference should be emphasized :

- "Full Disclosure" served the purpose of formal and complete description of a bidding system to be maintained on BBO server. The readability of the code is extremely low due to the complexity 
- BBOalert is strictly for personal use and should help to automate the disclosure of specific agreements. The simplicity of the code makes it readable.

## Installation

### Firefox

This extension can be installed with Firefox browser using the link :

https://addons.mozilla.org/en-US/firefox/addon/bboalert

Windows, Linux and Android platforms are supported

### Chrome

The extension is not yet officially published in Google's web-store. Therefore you should install it in CHROME browser manually from source code :

- download BBOalert project source files in a ZIP-container ("Clone or Download" button, then "Download ZIP")
- Navigate to the "Downloads" directory, open the ZIP-container and expand it. This will create a subdirectory "BBOalert-master" containing project's source files.
- open Chrome browser session with URL "chrome://extensions"
- make sure the Developer Mode is switched ON (in right-upper corner)
- click at "Load Unpacked" button and navigate to the "BBOalert-master" directory and confirm. BBOalert should appear on the list of installed extensions

Note : CHROME does not support extensions under Android. You should use YANDEX browser instead. The installation procedure is identical, except the last step : you should select the manifest.json file to complete the installation.

## Function

BBOalert communicates thru clipboard using CSV formatted text :

- at BBO startup, the clipboard must contain the table of alerted calls
- at the end of the BBO session, clipboard will contain the list of manually entered or modified alerts. You will be able to append this data by pasting it at the end of the file.

The first line must begin with "BBOalert" keyword. Other lines should contain at least three text fields separated by commas:

  - bidding sequence preceding the alerted call including opponent's calls
  - your bidding call
  - explanation text

The calls should be coded using two-character keywords: 1C 1D 1H 1S 1N Db Rd --

The keyword -- is used for pass for better readability.
In the explanation field, comma must be avoided.
Each field may contain leading or trailing spaces or tabs for better readability during coding.
Fourth field is optional and may be used for comments

You can also define keyboard shortcuts which are expanded to the predefined text while typing.

See 'sample.txt' file for more information.

## How to use

To use BBOalert you should :

- open the table file with your favorite text editor and keep it open until the end of the BBO session.
- select all text
- copy it to clipboard
- open BBO session using URL https://www.bridgebase.com/v3/?lang=en
- after you correctly login into BBO, the message should appear confirming that the table has been loaded from clipboard

If you alert manually during the game, the clipboard shall contain the text to be appended to the table file by pasting it. In the text editor, navigate to the end of the file, and do 'Paste', The records imported from BBO alert will contain a timestamp and the deal number. You can retrieve from BBO the deals to review the alerted calls before commiting the changes.

"Confirm bids" option in BBO ("Account" + "Settings") is required to be able to enter or review alert's explanation before confirming the call.

## Recommended way

We recommend the "You only alert once" principle.

It is needless to code your entire system at once. It is a huge task. In each artificial bidding system there are sequences which occur almost never.

The program records each alerted call for which no explanation has been found in the data file. Use this feature to complete your code with the bidding sequences as they come during the game. I recommend to to proceed this way :

- Instead of a simple text editor, create a new file in Google Docs beginning with the keyword BBOalert
- make this file "Sharable" with write access for your partner and send him the URL link. This guarantees to be always in sync.
- enter the code for opening bids and frequently used responses
- start playing using this data (remember : select all text + copy to clipboard before starting BBO session)
- alert your calls by hand if necessary
- at the end of the session, paste the clipboard content at the end of the file. Your partner should do it too.

This way, the file is ready for the next session and will contain recently alerted calls.
