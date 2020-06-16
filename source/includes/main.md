# Hotels Web Services API - Developers Guide
**Version 5.0.0**<br>
**5 February 2020**
# Introduction & Accreditation Process

## About this guide
Welcome to the YouTravel Hotels Web Services API Developers Guide
This document describes access using http POST or GET method. 
The http response will be of type "text/xml" using ISO-8859-1 encoding and will contain the response XML.

To help you navigate the docs, this page is split into 3 vertical sections:
- the navigation menu and search on the left,
- the content in the middle,
- and usage examples on the right.

<aside class="notice">
For security purposes we require static IP addresses otherwise the access to the feed won’t be authorized.
</aside>

## Server details for availability and prebook requests
**Test server**<br>
availURL: <a href="http://testxml.youtravel.com/webservices/" target="_blank">`http://testxml.youtravel.com/webservices/`</a><br>
Username: `xmltestme`<br>
Password: `testme`

**Production server**<br>
availURL: <a href="http://xmlapi.youtravel.com/webservices/" target="_blank">`http://xmlapi.youtravel.com/webservices/`</a><br>
Username: `your username`<br>
Password: `your password`

**Live Access**
As part of the final stages of testing there is an accreditation process necessitating sign off from our XML support team.<br>
There are two phases of Accreditation one in test the other live; this includes checking all xml request & response messaging.

<aside class="notice">
  <b>IP Whitelisting:</b> to obtain a successful response from our live web service we require your known IP range,
</aside>

## Server details for booking and canrequests
**Test server**<br>
bookURL: <a href="http://testxml.youtravel.com/webservices/" target="_blank">`http://testxml.youtravel.com/webservices/`</a><br>

**Production server**<br>
bookURL: <a href="http://book.youtravel.com/webservices/" target="_blank">`http://book.youtravel.com/webservices/`</a><br>


## Testing best practices
1. Lead name : `Mr Test Test`
2. Book at least 3 months in advance
3. Hotel ID: `1572` (Test Hotel EU)


# Availability

## Availability Search Request and Response
> Request URL
```plaintext
availURL/index.asp
```

> Example request by **airport**
```plaintext
availURL/index.asp?Dstn=FAO&LangID=EN&Username=xmltestme&Password=testme&...
```

> Example request by **hotel id**
```plaintext
availURL/index.asp?HID=1572&LangID=EN&Username=xmltestme&Password=testme&...
```

> Example error response
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<HtSearchRq>
  <Success>False</Success>
  <ErrorMsg>No Results Found.</ErrorMsg>
</HtSearchRq>
```
> Example successful response
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<HtSearchRq xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="http://xml.youtravel.com/webservices/xsd_yt_srq.xsd">
    <Success>true</Success>
    <Search_Criteria>
        <Company>XML Test Affiliate</Company>
        <LangID>EN</LangID>
        <Dstn>ayt</Dstn>
        <Rsrt></Rsrt>
        <Rooms>1</Rooms>
        <Nofn>7</Nofn>
        <Checkin_Date>02/11/2020</Checkin_Date>
        <Youtravel_Rating>1</Youtravel_Rating>
        <Board_Type>ALL</Board_Type>
        <Adlts_1>2</Adlts_1>
        <Child_1>0</Child_1>
        <Infant_1>0</Infant_1>
        <Adlts_2>0</Adlts_2>
        <Child_2>0</Child_2>
        <Infant_2>0</Infant_2>
        <Adlts_3>0</Adlts_3>
        <Child_3>0</Child_3>
        <Infant_3>0</Infant_3>
    </Search_Criteria>
    <session id="1011023528397202030464313">
        <Currency>EUR</Currency>
        <Hotel ID="38493">
            <Hotel_Name>Barut Arum</Hotel_Name>
            <Youtravel_Rating>5</Youtravel_Rating>
            <Official_Rating>5 Stars</Official_Rating>
            <Board_Type>(AI)</Board_Type>
            <Child_Age>-</Child_Age>
            <Country>Turkey</Country>
            <Destination>Antalya</Destination>
            <Resort>Side</Resort>
            <Image>https://images.youtravel.com/photos/get_hotel_photo.aspx?id=3245088_9CE3A43DDFDADE9448B8D86393DCFA7A37D1B717C07A15CFF39E4223CA3502CB</Image>
            <Hotel_Desc><![CDATA[directly at the beach; beach details: private sandy beach; distance (approx.): t]]></Hotel_Desc>
            <Room_1>
                <Passengers Adults="2" Children="0" Infants="0"></Passengers>
                <Room Id="AYT001D2DSL:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDeDSL_DR_AI_yaeapapaaaaaiadtjgpyaa"/>
                    <Type>Superior Twin/Double Room Land View</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="859.01" Final_Rate="859.01"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT001D2DS:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDeDS_DR_AI_yaeapapaaaaaiajqtgwaa"/>
                    <Type>Superior Twin/Double Room</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="975.3" Final_Rate="975.3"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT001D2DXM:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDeDXM_DR_AI_yaeapapaaaaaiayybigbiaa"/>
                    <Type>Deluxe Twin/Double Room Sea View</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="1164.64" Final_Rate="1164.64"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT001D2PX:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDePX_DR_AI_yaeapapaaaaaiaywwygeaa"/>
                    <Type>Deluxe Suite</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="1331.2" Final_Rate="1331.2"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT001D2FZ:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDeFZ_DR_AI_yaeapapaaaaaiaywjqgtyaa"/>
                    <Type>Family Room</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="1397.51" Final_Rate="1397.51"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT001D2PI:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDePI_DR_AI_yaeapapaaaaaiayiyqgywaa"/>
                    <Type>Suite</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="1417.13" Final_Rate="1417.13"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT001D2PHM:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqawdijwaAYTppyDePHM_DR_AI_yaeapapaaaaaiaytyigpdaa"/>
                    <Type>Penthouse Suite Sea View</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="1514.08" Final_Rate="1514.08"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
            </Room_1>
        </Hotel>
        <Hotel ID="18800">
            <Hotel_Name>Kahya Hotel</Hotel_Name>
            <Youtravel_Rating>4</Youtravel_Rating>
            <Official_Rating>4 Stars</Official_Rating>
            <Board_Type>(AI)</Board_Type>
            <Child_Age>-</Child_Age>
            <Country>Turkey</Country>
            <Destination>Antalya</Destination>
            <Resort>Alanya</Resort>
            <Image>https://images.youtravel.com/photos/get_hotel_photo.aspx?id=3244967_3C43F7CFF89D9CA9713884C3511E30C4327F6072F8518FDFC18EFAF999D49B50</Image>
            <Hotel_Desc><![CDATA[directly at the beach, only separated by the coastal road; beach details: sandy/]]></Hotel_Desc>
            <Room_1>
                <Passengers Adults="2" Children="0" Infants="0"></Passengers>
                <Room Id="GZP0005GDM:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqayddppaGZPppptGDM_DR_AI_yaeapapaaaaaiawptgyjaa"/>
                    <Type>EconomyTwin/Double Room</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="305.19" Final_Rate="305.19"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="GZP0005GDZL:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqayddppaGZPppptGDZL_DR_AI_yaeapapaaaaaiawwpgebaa"/>
                    <Type>Twin/Double Room Land View</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="330.26" Final_Rate="330.26"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="GZP0005GDZK:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqayddppaGZPppptGDZK_DR_AI_yaeapapaaaaaiawtdgwwaa"/>
                    <Type>Twin/Double Room Side Sea View</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="358.33" Final_Rate="358.33"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
            </Room_1>
        </Hotel>
        <Hotel ID="12617">
            <Hotel_Name>Nirvana Lagoon Villas Suites &amp;amp; Spa</Hotel_Name>
            <Youtravel_Rating>5</Youtravel_Rating>
            <Official_Rating>5 Stars</Official_Rating>
            <Board_Type>(AI)</Board_Type>
            <Child_Age>-</Child_Age>
            <Country>Turkey</Country>
            <Destination>Antalya</Destination>
            <Resort>Kemer</Resort>
            <Image>https://images.youtravel.com/photos/get_hotel_photo.aspx?id=3245171_E2E8C052826C40279EBBE1E07EC16B0999C31778EC1C21E9E56926512DA8B1B2</Image>
            <Hotel_Desc><![CDATA[directly at the beach; beach details: private sandy/shingle beach; beach informa]]></Hotel_Desc>
            <Room_1>
                <Passengers Adults="2" Children="0" Infants="0"></Passengers>
                <Room Id="AYT004PUDZ:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqayebyqaAYTppiPUDZ_DR_AI_yaeapapaaaaaiaitybgttaa"/>
                    <Type>Twin/Double Room</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="4516.55" Final_Rate="4516.55"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT004PUDS:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqayebyqaAYTppiPUDS_DR_AI_yaeapapaaaaaiaitybgttaa"/>
                    <Type>Superior Twin/Double Room</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="4516.55" Final_Rate="4516.55"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
                <Room Id="AYT004PUFZ:DR:AI:1" Refundable="true">
                    <CanxPolicy token="epepyypeaepepyypjaqayebyqaAYTppiPUFZ_DR_AI_yaeapapaaaaaiaitybgttaa"/>
                    <Type>Family Room</Type>
                    <Board>AI</Board>
                    <Rates Original_Rate="4516.55" Final_Rate="4516.55"></Rates>
                    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
                </Room>
            </Room_1>
        </Hotel>
    </session>
</HtSearchRq>
```



------------

**Request Parameters**

| Field  | Meaning   | Type   | Format   | Comment   |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| HID     | Hotel ID   | Numeric   |   |   |
| Checkin_Date  | Check-in date  | Date  | dd/mm/yyyy  |   |
| Nights  | Number of nights | Numeric |   | Maximum number of nights is 99  |
| Rooms | Number of rooms | Numeric | Maximum number of rooms is 3|
| ADLTS_1 | Number of adults in 1st room | Numeric |  | Maximum number of adults per room is 6 |
| CHILD_1 | Number of children in 1st room | Numeric | | Maximum number of children per room is 4 |
| ADLTS_2 | Number of adults in 2nd room | Numeric | | Maximum number of adults per room is 6 |
| CHILD_2 | Number of children in 2nd room | Numeric | | Maximum number of children per room is 4 |
| ADLTS_3 | Number of adults in 3rd room | Numeric | | Maximum number of adults per room is 6 |
| CHILD_3 | Number of children in 3rd room | Numeric | | Maximum number of children per room is 4 |
| ChildAgeR1C1 | Age for the 1st child in the 1st Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR1C2 | Age for the 2nd child in the 1st Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR1C3 | Age for the 3rd child in the 1st Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR1C4 | Age for the 4th child in the 1st Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR2C1 | Age for the 1st child in the 2nd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR2C2 | Age for the 2nd child in the 2nd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR2C3 | Age for the 3rd child in the 2nd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR2C4| Age for the 4th child in the 2nd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR3C1 | Age for the 1st child in the 3rd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR3C2 | Age for the 2nd child in the 3rd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR3C3 | Age for the 3rd child in the 3rd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| ChildAgeR3C4 | Age for the 4th child in the 3rd Room | Numeric | 2-14 Child (-1 or 1 for Infant) | 2-14 for child. If child is < 2. Then apply as infant |
| BT | All board categories | Numeric | 1 | All combinations of board categories can be used |
| BT_RO | Room only category | Numeric | 1 | All combinations of board categories can be used |
| BT_SC | Self catering category | Numeric | 1 | All combinations of board categories can be used |
| BT_BB | Bed & breakfast category | Numeric | 1 | All combinations of board categories can be used |
| BT_HB | Half board category | Numeric | 1 | All combinations of board categories can be used |
| BT_FB | Full board category | Numeric | 1 | All combinations of board categories can be used |
| BT_AI | All inclusive category | Numeric | 1 | All combinations of board categories can be used |
| BT_VILLA | Villa category | Numeric | 1 | All combinations of board categories can be used |
| StarCatAll | All youtravel.com star categories | Numeric | 1 | All combinations of star categories can be used |
| StarCat1 | Youtravel.com 1 star category | Numeric | 1 | All combinations of star categories can be used |
| StarCat2 | Youtravel.com 2 stars category | Numeric | 1 | All combinations of star categories can be used (1\*and 2\* hotels will be shown as well with the 2\*) |
| StarCat3 | Youtravel.com 3 stars category | Numeric | 1 | All combinations of star categories can be used (2\*and 3\* hotels will be shown as well with the 3\*) |
| StarCat4 | Youtravel.com 4 stars category | Numeric | 1 | All combinations of star categories can be used (4\*and 5\* hotels will be shown as well with the 5\*) |
| LangID | Language | String(2) | EN | Supported Languages <br>EN: English |
| Username | | String(15) | Account info | Max 15 alphanumeric Digits |
| Password | | String(10) | Account | Max 10 alphanumeric Digits |


<aside class="notice">
    ADLTS_1 and CHILD_1 in the request will match Room_1 in the response (same for ADLTS_2 with Room_2 etc)
</aside>


## Board option descriptions
boardURL: <a href="https://www.youtravel.com/boardoptions_popup.asp" target="_blank">`https://www.youtravel.com/boardoptions_popup.asp`</a>

**Deep Link**<br>
Special search request criteria can be used to retrieve a deep link to the youtravel.com website from the XML feed.
<style type="text/css">
    ol { list-style-type: upper-alpha; }
</style>
1. ShowLink=1 (Support for agent searches only B2B)
2. ShowLink=2 (Support for direct customers only B2C)

## Availability & prices search response

**Response parameters**

| Field  | Meaning  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| Session_ID  |   | Numeric  |   | Necessary to make the booking  |
| Success |   | Boolean  | True or false   | Clarifies if the search is successful   |
| Company  |   | String  |   | Search criteria value  |
| LangID  |   | String  |   | Search criteria value  |
| Dstn | | String | | String Search criteria value |
| Rsrt | | Numeric | | Search criteria value |
| Rooms | | Numeric | | Search criteria value |
| Nofn | | Numeric | | Search criteria value |
| Checkin_Date | | String | | Search criteria value |
| Youtravel_Rating | | Numeric | | Search criteria value |
| Board_Type | | String | | Search criteria value |
| Adlts_1 | | Numeric | | Search criteria value |
| Child_1 | | Numeric | | Search criteria value |
| Infant_1 | | Numeric | | Search criteria value |
| Adlts_2 | | Numeric | | Search criteria value |
| Child_2 | | Numeric | | Search criteria value |
| Infant_2 | | Numeric | | Search criteria value |
| Adlts_3 | | Numeric | | Search criteria value |
| Child_3 | | Numeric | | Search criteria value |
| Infant_3 | | Numeric | | Search criteria value |
| Currency | | String | | |
| Hotel_ID | | Numeric | | |
| Hotel_Name | | String | | |
| Youtravel_Rating | | String | 1, 1+, 2, 2+, 3, 3+, 4,4+, 5, 5+ |  |
| Official_Rating | | String | | Rating given to property by local tourist board |
| Board_Type | | String | RO,SC,BB,HB,FB,AI, VILLA | RO : Room only <br>SC: Self catering <br>BB: Bed & Breakfast <br> HB: Half Board <br> FB: Full Board |
| Child_Age | | Numeric | | Between 2-14 years old |
| Country | | Numeric | | |
| Destination | | String | | |
| Resort | | String | | |
| Image | | String | | Hotel thumbnail |
| Hotel_Desc | | String | | Short hotel description up to 80 Characters |
| Room_1<br>Room_2<br>Room_3 | GROUP<br>FIELDS | |  |  |
| Room Id | | | Alphanumeric(30) | Room identification number |
| Refundable | | String | True or False | true if Room is Refundable |
| Passengers |  | Numeric |  | Number of Adults, Children and Infants in the room |
| Type | | String |  | Room type and view room type |
|  Board |  | String | RO, SC, BB, HB, FB, AI,FB-LC,FB-FE | RO: Room only <br>SC: Self catering <br>BB: Bed & Breakfast <br>HB: Half Board <br>FB: Full Board <br>AI: All Inclusive <br>FB-LE: Full Board with light excursions <br>FB-FE: Full Board with full excursions |
| Rates |  | Numeric |  | Original rate: Rate before offer applies <br>Final rate: Rate after offer applies |
| Offers |  | Numeric | 0: Offer not applies <br> 1: Offer applies | Lastminute_offer: Special discount price <br> Early_Booking_Discount: Discount for early bookings <br> Free_Stay: One or more nights free based on number of stays <br> Free_Transfer: Free transfer is included in the price <br> Gala_Meals: Special event meals included in price |

## Show Board Type – (LIGHT), (STANDARD), (CLASSIC), (PREMIER)
>Example request
```plaintext
boardURL/index.asp?Checkin_Date=24/09/2013&Username=xmltestme&Password=testme&Nights=7&LangID=EN&Rooms=1&ADLTS_1=2&Dstn=RHO&Currency=GBP&StarCatAll=1&BT=1&SBT=1
```

> Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<Success>true</Success><Search_Criteria>
    <Company>XML Test Affiliate</Company>
    <LangID>EN</LangID>
    <Dstn>RHO</Dstn>
    <Rsrt />
    <Rooms>1</Rooms>
    <Nofn>7</Nofn>
    <Checkin_Date>24/09/2013</Checkin_Date>
    <Youtravel_Rating>Allstarratings</Youtravel_Rating>
    <Board_Type>1</Board_Type>
    <Adlts_1>2</Adlts_1>
    <Child_1>0</Child_1>
    <Infant_1>0</Infant_1>
    <Adlts_2>0</Adlts_2>
    <Child_2>0</Child_2>
    <Infant_2>0</Infant_2>
    <Adlts_3>0</Adlts_3>
    <Child_3>0</Child_3>
    <Infant_3>0</Infant_3>
</Search_Criteria><session id="1076622456192201324050110">
    <Currency>EUR</Currency>
    <Hotel ID="9288">
        <Hotel_Name>Golf View Hotel</Hotel_Name>
        <Youtravel_Rating>3</Youtravel_Rating>
        <Official_Rating>3 stars</Official_Rating>
        <Board_Type>(AI)</Board_Type>
        <Child_Age>2 - 12</Child_Age>
        <Country>Greece</Country>
        <Destination>Rhodes</Destination>
        <Resort>Afandou</Resort>
        <Image>http://images.youtravel.com/photos/9288/xml.jpg</Image>
        <Hotel_Desc>
            <![CDATA[Built on a hill with a wonderful view of the sea and on the entrance of the
town]]>
        </Hotel_Desc>
        <Room_1>
            <Passengers Infants="0" Children="0" Adults="2" />
            <Room Id="255825" Refundable= ”true”>
                <Type>Double/Twin Room</Type>
                <Board>AI</Board>
                <AI_Type>LIGHT</AI_Type>
                <Rates Final_Rate="243.04" Original_Rate="303.8" />
                <Offers Gala_Meals="0" Free_Transfer="0" Free_Stay="0" Early_Booking_Discount="0" Lastminute_Offer="1" />
            </Room>
        </Room_1>
    </Hotel>
```

To receive the Board Type where more than one category of the same board exists submit “**SBT=1**” (show board type)
<br>SBT=1 = True
<br>SBT=0 = False
<br>These categories only apply to All Inclusive (AI).
<br>Only one `<AI_TYPE>` will be displayed per Room Id
<a href="https://www.youtravel.com/explanation_ai.asp" target="_blank">https://www.youtravel.com/explanation_ai.asp</a>

# Property sorting

## Suggested property
> Enable suggestions request parameter
```
YTS=1
```

> Example request
```plaintext
availURL/index.asp?Checkin_Date=30/09/2013&Username=xmltestme&Password=testme&Nights=7&LangID=EN&Rooms=2&ADLTS_1=2&ADLTS_2=1&Dstn=TFS&Currency=GBP&StarCatAll=1&BT=1&YTS=1
```

> Example response<br>
> *The result will appear with 1to 5. Please note it is possible to have more than 1 of the
same priority in any response.*
```xml
<Hotel ID="2299">
    <Hotel_Name>Blue Sea Callao Garden</Hotel_Name>
    <Youtravel_Rating>3</Youtravel_Rating>
    <Official_Rating>3 stars</Official_Rating>
    <YT_Suggested>1</YT_Suggested>
    <Board_Type>(SC)(AI)</Board_Type>
    <Child_Age>2 - 12</Child_Age>
    <Country>Canaries</Country>
    <Destination>Tenerife</Destination>
    <Resort>Callao Salvaje</Resort>
    <Image>http://images.youtravel.com/photos/2299/xml.jpg</Image>
    <Hotel_Desc>
        <Blue Sea Callao Garden is a hotel complex situated in the southeast of the]]>
    </Hotel_Desc>
    <Room_1>
        <Passengers Adults="2" Children="0" Infants="0" />
        <Room Id="202550" Refundable= ”True”>
            <Type>1 Bedroom Apartment Garden View</Type>
            <Board>SC</Board>
            <Rates Original_Rate="223.81" Final_Rate="193.44" />
            <Offers Lastminute_Offer="1" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0" />
        </Room>
        <Room Id="202551" Refundable= ”True”>
            <Type>1 Bedroom Apartment Standard All Inclusive</Type>
            <Board>AI</Board>
            <Rates Original_Rate="432.44" Final_Rate="432.44" />
            <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0" />
        </Room>
    </Room_1>
</Hotel>
```

YouTravel can suggest the best properties to display first based on pricing, availability and over customer rating of a property.

## Show Rooms Remaining
> Remaining rooms request Parameter
```
SRR=1
```
> Response
```xml
<Passengers Infants="0" Children="0" Adults="2" /><Room Id="366105" Refundable= ”True”>
    <Type>Standard Double/Twin Room</Type>
    <Board>BB</Board>
    <Rates Final_Rate="183.45" Original_Rate="183.45" />
    <Offers Gala_Meals="0" Free_Transfer="0" Free_Stay="0" Early_Booking_Discount="0" Lastminute_Offer="0" Rooms_remaining="2" />
```

To show rooms remaining this is a requestable element and will appear as an additional attribute shown in Offers .
Rooms reaming will show a Min 1 and max 9 for any given roomtype.

## Sort Results by
> Sort by highest price first :
```
SBE=1
```
> Sort by lowest price first :
```
SBC=1
```

Parameters for sorting results

# Destination and resort information request
> Request to URL/get_destinations.asp
```plaintext
availURL/get_destinations.asp?LangID=EN&Username=xmltestme&Password=testme
```

>Example of the destinations & resort information response
```xml
<?xml version= “1.0” encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <LangID>EN</LangID>
    <Country ID="5" Name="Canaries" Code="ES">
    <Destination ID="37" name="Fuerteventura">
        <ISO_Codes Code_3="" Code_2="" Code_1="FUE" />
        <Resort ID="138">
            <Resort_Name>Antigua</Resort_Name>
        </Resort>
        <Resort ID="136">
            <Resort_Name>Caleta de Fuste</Resort_Name>
        </Resort>
        <Resort ID="92">
            <Resort_Name>Corralejo</Resort_Name>
        </Resort>
        <Resort ID="140">
            <Resort_Name>Costa Calma</Resort_Name>
        </Resort>
        <Resort ID="139">
            <Resort_Name>El Cotillo</Resort_Name>
        </Resort>
        <Resort ID="137">
            <Resort_Name>Las Playitas</Resort_Name>
        </Resort>
        <Resort ID="545">
            <Resort_Name>Nuevo Horizonte-El Castillo</Resort_Name>
        </Resort>
        <Resort ID="359">
            <Resort_Name>Pajara</Resort_Name>
        </Resort>
        <Resort ID="285">
            <Resort_Name>Playa Barca</Resort_Name>
        </Resort>
        <Resort ID="544">
            <Resort_Name>Playa de Esquinzo</Resort_Name>
        </Resort>
        <Resort ID="141">
            <Resort_Name>Playa Jandia Morro Jable</Resort_Name>
        </Resort>
    </Destination>
```

***Request parameters***

| Name   | Type   | Format   | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| LangID  | String  | EN  | EN: English |
| Username  | String(15)   |   | Account info  |
| Password | String(10) | | Account info |

<br>

------------

<br>

***Response parameters***

| Name  | Type   | Format   | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Success  | Boolean  | True or False  | Clarifies if the request is successful  |
| LangID  | String  | EN | EN: English  |
| Country_ID  | String  |   |   |
| Name  | String  |   |   |
| Country_Code  | String  |   |   |
| Destination  | String  |   |   |
| Name  | String  |   |   |
| ISO_Codes  | String  | ISO  |   |
| Resort_ID  | Numeric  |   |   |
| Resort_Name | String | | |

# Hotel Detailed Description
> Request to URL/get_hoteldetails.asp
```plaintext
availURL/get_hoteldetails.asp?LangID=EN&HID=1&Username=xmltestme&Password=testme
```

> Avalilability Response<br>
> *As opposed to the Room type name being displayed as shown in the availability response.*
```xml
<Type>Double/Twin Room Landview</Type>
<Room name="Double Twin Room Landview">
```

> Hotel Description Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <LangID>EN</LangID>
    <Destination>Emilia Romagna - Riccione</Destination>
    <HID>9053</HID>
    <Hotel Name="Promenade Hotel">
        <Youtravel_Rating>4</Youtravel_Rating>
        <Official_Rating>4 stars</Official_Rating>
        <Board_Type>(BB)(AI))</Board_Type>
        <Hotel_Desc>
            <![CDATA[Located only 10 metres from sandy beach and only a few steps from Viale
Ceccarini; the most exclusive shopping area of Riccione, The Promenade Hotel
offers boutique accommodation facing the Adriatic Sea. The hotel features an indoor
pool with heated seawater and whirlpool corner. Other facilities include SPA with
sauna, Turkish bath, massage and beauty treatment, free Wi-Fi just to name a few.
The hotel also features a restaurant which serves buffet breakfast and offers a choice
among 3 menus for lunch and dinner. The bar is 24hrs open. The rooms are
equipped with Wi-Fi, Minibar and a safety box. The hotel is conveniently located and
is only 1.5 km away from train station while 5 km from airport.]]>
        </Hotel_Desc>
        <Hotel_Photos>
            <Photo>http://images.youtravel.com/photos/9053/xml.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/pool11.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/pool2.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/reception.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/exterior.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/lobby.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/main.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/room1.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/room2.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/restaurnat.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/restaurnt1.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/lobby1.jpg</Photo>
            <Photo>http://images.youtravel.com/photos/9053/indoor Pool.jpg</Photo>
        </Hotel_Photos>
        <Hotel_Facilities>
            <Facility>Baby cot(on request)</Facility>
            <Facility>Bar(s)</Facility>
            <Facility>Beauty salon(extra charge)</Facility>
            <Facility>Massage (extra charge)</Facility>
            <Facility>Restaurant(s)</Facility>
            <Facility>Sauna</Facility>
            <Facility>Small Pets Allowed</Facility>
            <Facility>SPA</Facility>
            <Facility>Swimming Pool Indoor - Heated</Facility>
            <Facility>Turkish Bath</Facility>
            <Facility>Wi Fi Internet Connection</Facility>
        </Hotel_Facilities>
        <Room_Types>
            <Room name="Twin Room Side Sea View (A )">
                <Facility>Air Conditioning</Facility>
                <Facility>Bathroom with shower</Facility>
                <Facility>Mini Bar</Facility>
                <Facility>Safety Box</Facility>
                <Facility>Sat TV</Facility>
                <Facility>Telephone</Facility>
                <Facility>Terrace Balcony</Facility>
                <Facility>Wi Fi Internet Connection (Free of Charge)</Facility>
            </Room>
        </Room_Types>
        <AI_Type>STANDARD</AI_Type>
        <AI_Desc>
            <MEALS Breakfast buffet (Crown restaurant: 07:00-10:00) Lunch buffet (Crown Restaurant:12:30-15:00) Dinner buffet (Crown restaurant: 18:00-21:00 winter)>
        </AI_Desc>
        <AI_Facilities>
            <AI_Facility>Aerobic</AI_Facility>
            <AI_Facility>Animation</AI_Facility>
            <AI_Facility>Aqua Aerobics</AI_Facility>
            <AI_Facility>Archery</AI_Facility>
            <AI_Facility>Badminton</AI_Facility>
            <AI_Facility>Basketball</AI_Facility>
        </AI_Facilities>
        <Erratas>
            <![CDATA[Please Note Due to recent Tourist Tax Regulations all bookings
might be subjected to an additional charge (fixed per destination/hotel) paid
locally at the Hotel. City tax 2.50 per person / per day.(Tax is to pay for
Maximum 7 nights. Children till 13.9 years dont have to pay for tax.) ]]>
        </Erratas>
    </Hotel>
</HtSearchRq>
```

On the get_hoteldetails RS the data fetched passes from an extra filtering
(escapeHTML) where characters are transformed before being rendered; these are:
<br>`'<' to '&lt'`
<br>`'>' to '&gt'`
<br>`'&' to 'and'`
<br>`'''' to ''`
<br>`'/' to ' '`
<br>`'\' to ' '`
<br>`'' to ''`

***Request parameters***

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| LangID  | String  | EN  | EN: English  |
| HID  | Numeric(15)  |   |   |
| Username  | String(15)  |   | Account info  |
| Password  | String(10)  |   | Account info  |

<br>

------------

<br>

***Response parameters***

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Success  | Boolean  | True or False  | Clarifies if the request is successful  |
| LangID  | String  | EN  | EN: English  |
| HID | Numeric(15) | | |
| Destination | Numeric | | Destination and resort |
| Hotel_Name | String | | |
| Youtravel_Rating | String | 1, 2, 2+, 3, 3+, 4,4+, 5,5+ | |
| Official_Rating | String | | |
| Board_Type | String | | |
| Hotel_Desc | String | | Detailed hotel description |
| Hotel_Photos | String | | |
| Room_Types | GROUP FIELD | | |
| Room_Name | String | | |
| Facility | String | | |
| AI_Type | String | | LIGHT, STANDARD, CLASSIC, PREMIER |
| AI_Desc | String | | Detailed board description | 
| AI_Facilities | String | | |
| Erratas | String | | |


## Additional information in get_hoteldetails.asp

> Request parameter in URL/get_hoteldetails.asp
```
SHA=1
```
> Request example
```plaintext
availURL/get_hoteldetails.asp?LangID=EN&HID=2970&Username=xmltestme&Password=testme&sha=1
```

> Response
```xml
<HtSearchRq>
    <Success>True</Success>
    <LangID>EN</LangID>
    <Destination>Sharm El Sheikh - Sharm El Sheikh</Destination>
    <HID>2970</HID>
    <Hotel Name="Savoy Hotel">
        <Youtravel_Rating>5</Youtravel_Rating>
        <Official_Rating>5 stars</Official_Rating>
        <Board_Type />
        <Hotel_Address>
            <Address>Sharm White Knight Beach</Address>
            <Post_Code />
            <City>Sharm El Sheikh</City>
            <Phone>0020 693602500</Phone>
            <Fax />
        </Hotel_Address>
```

##  Maximum and minimum child age in individual hotel
> Request parameter in URL/get_hoteldetails.asp
```
SCA=1
```

> Request example
```plaintext
availURL/get_hoteldetails.asp?LangID=EN&HID=2970&Username=xmltestme&password=testme&sca=1
```
> Response
```xml
<HtSearchRq>
    <Success>True</Success>
    <LangID>EN</LangID>
    <Destination>Sharm El Sheikh - Sharm El Sheikh</Destination>
    <HID>2970</HID>
    <Hotel Name="Savoy Hotel">
        <Youtravel_Rating>5</Youtravel_Rating>
        <Official_Rating>5 stars</Official_Rating>
        <Board_Type />
        <MinChildAge>2</MinChildAge>
        <MaxChildAge>11</MaxChildAge>
```

# Prebook
> Request
```plaintext
availURL/webservices/index.asp?Checkin_Date=30/09/2013&Username=xmltestme&Password=testme&Nights=7&LangID=EN&Rooms=2&ADLTS_1=2&ADLTS_2=1&Dstn=TFS&Currency=GBP&StarCatAll=1&BT=1&YTS=1&CanxPol=1
```
> Room search response
```xml
<Room Id="846166" Refundable="true">
    <CanxPolicy token="dibybbabbegpiaiaepyqpqpy" />
    <Type>Twin Room</Type>
    <Board>BB</Board>
    <Rates Original_Rate="662.04" Final_Rate="662.04"></Rates>
    <Offers Lastminute_Offer="0" Early_Booking_Discount="0" Free_Stay="0" Free_Transfer="0" Gala_Meals="0"></Offers>
</Room>
```
> CanxPolicy token to be during the prebook stage to retrieve cancellation rules<br>
> Get cancellation policy response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success></Success>
    <Room>724129</Room>
    <Policies>
        <Policy>
            <FromDate>22/12/2016</FromDate>
            <Fees>30.00</Fees>
            <Currency>EUR</Currency>
        </Policy>
        <Policy>
            <FromDate>12/12/2016</FromDate>
            <Fees>20.00</Fees>
            <Currency>EUR</Currency>
        </Policy>
        <Policy>
            <FromDate>02/12/2016</FromDate>
            <Fees>10.00</Fees>
            <Currency>EUR</Currency>
        </Policy>
    </Policies>
</HtSearchRq>
```

Before proceeding to the booking stage, you should retrieve the cancellation terms for a given hotel room before committing.

When sending a search request as detailed in section 3.0, you may add an additional parameter to the query string to emit cancellation tokens:

# Hotel booking
> Request to URL/bookings.asp
```plaintext
bookURL/bookings.asp?LangID=EN&HID=1572&Username=xmltestme&Password=testme&Cust_ResID=9879&requests=SpecialRequests....
```
> Hotel booking response
```xml
<?xml version= “1.0” encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>true</Success>
    <Booking_ref>102114011</Booking_ref>
    <Voucher_Url>http://vouchers.youtravel.com/voucher.asp?ID=102114011_ad92f6965e2ef197428f6e6e42cd6d72</Voucher_Url>
</HtSearchRq>
```

| Field  | Meaning  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| Session_ID  |   | Numeric  |   | Provided by the search response  |
| Checkin_Date  | Check-in date  | Date  | dd/mm/yyyy  |   |
| Nights  | Number of nights  | Numeric  |   | Max no. of nights is 40  |
| Rooms  | Number of rooms  | Numeric  |   | Max no. of rooms is 3  |
| ADLTS_1  | Number of adults in 1st room  | Numeric  |   | Max no. of Adults per room is 6  |
| CHILD_1  | Number of children in 1st room  | Numeric  |   | Max no. of children per room is 4  |
| ADLTS_2  | Number of adults in 2nd room  | Numeric  |   | Max no. of Adults per room is 6  |
| CHILD_2  | Number of children in 2nd room  | Numeric  |   | Max no. of children per room is 4  |
| ADLTS_3  | Number of adults in 3rd room  | Numeric  |   | Max no. of Adults per room is 6  |
| CHILD_3  | Number of children in 3rd room  | Numeric  |   | Max no. of children per room is 4  |
| ChildAgeR1C1 | Age for the 1st child in the 1st room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR1C2 | Age for the 2nd child in the 1st room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR1C3 | Age for the 3rd child in the 1st room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR1C4 | Age for the 4th child in the 1st room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR2C1 | Age for the 1st child in the 2nd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR2C2 | Age for the 2nd child in the 2nd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR2C3 | Age for the 3rd child in the 2nd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR2C4 | Age for the 4th child in the 2nd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR3C1 | Age for the 1st child in the 3rd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR3C2 | Age for the 2nd child in the 3rd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR3C3 | Age for the 3rd child in the 3rd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| ChildAgeR3C4 | Age for the 4th child in the 3rd room | Numeric | 2-14 for child -1 or 1 for infant | 2-14 for child. If child is < 2. Then counts as infant |
| LangID | Language | String(2) | EN | EN: English |
| HID | Hotel ID | Numeric |  | Max 15 Numeric Digits |
| RID | Room id for the 1st room | Alphanumeric |  | Max 30 alphanumeric characters |
| RID_2 | Room id for the 2nd room | Alphanumeric |  | Max 30 alphanumeric characters |
| RID_3 | Room id for the 3rd room | Alphanumeric |  | Max 30 alphanumeric characters |
| Customer_title | Customer title | String(10) | |Max 10 characters |
| Customer_firstname | Customer first name | String (40) | |Max 40 characters |
|  Customer_lastname | Customer last name | String(40) | |Max 40 characters |
| Room1_Rate | Final Rate for the 1st room as provided in the feed | Numeric | Up to 2 decimals |  |
| Room2_Rate | Final Rate for the 2nd room as provided in the feed | Numeric | Up to 2 decimals |  |
| Room3_Rate | Final Rate for the 3rd room as provided in the feed | Numeric | Up to 2 decimals | |
| Email | Email address that will receive the hotel voucher | String | | |
| Arr_Date | Customer flight arrival date Date | Date | dd/mm/yyyy | Optional only if no flight info to send |
| Arr_DepTime | Customer flight arrival time | Numeric | hhmm | Optional only if no flight info to send |
| Arr_flight_from | Departing airport | String | ISO | Max 3 Characters - Optional |
| Arr_flight_to | Arrival airport | String | ISO | Max 3 Characters - Optional |
| Arr_Flight_Num | Arrival flight number | String | | Optional only if no flight info to send |
| Dep_Date | Customer flight departure date | Date | dd/mm/yyyy | Optional only if no flight info to send |
| Dep_DepTime | Customer flight departure time | Numeric | hhmm | Optional only if no flight info to send |
| Dep_Flight_From | Departure airport | String | ISO | Max 3 Characters - Optional |
| Dep_Flight_To | Arrival airport | String | ISO | Max 3 Characters - Optional |
| Dep_Flight_Num | Departure flight number | String |  | Optional only if no flight info to send |
| Requests | Special Request | String | | Max 250 characters - optional |
| Username | Account information | String | Max 15 alphanumeric digits |
| Password | Account information | String | | Max 10 Alpa Numeric digits |

<aside class="notice">
    Special requests information will only appear in voucher. Special requests cannot be guaranteed and is at hotel’s discretion
</aside>

# Cancellation

## Cancel via web service
The cancellation message is used to retrieve cancellation fees for the given booking.
This must take place in 2 steps.
1. Request cancellation fees for specific booking
2. Finalizing cancellation.

## Cancellation fees request
> Request URL
```plaintext
bookURL/get_canx_fees.asp
```

> Request example
```plaintext
bookURL/get_canx_fees.asp?Booking_ref=10231122311233112&Username=xmltestme&password=testme
```
> Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <Booking_ref>10611091035573584</Booking_ref>
    <Fees>10.00</Fees>
    <Currency>EUR</Currency>
</HtSearchRq>
```

<aside class="notice">
This step will not cancel the booking; it will only display cancellation charge as of the requested date and time
</aside>

**Request Parameters**

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Booking_ref  |   | Numeric  | Booking reference  |
| Username  | Account information  | String(15)  | Max 15 alphanumeric Digits  |
| Password  | Account information  | String(10)  | Max 10 alphanumeric Digits  |


## Finalize Cancellation Request
> Request URL
```plaintext
bookURL/cancel.asp
```
> Request example
```plaintext
bookURL/cancel.asp?Booking_ref=10231122311233112&Username=xmltestme&password=testme
```
> Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <Booking_ref>10611091035573584</Booking_ref>
</HtSearchRq>
```

**Request Parameters**

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Booking_ref  |   | Numeric  | Booking reference  |
| Username  | Account information  | String(15)  | Max 15 alphanumeric Digits  |
| Password  | Account information  | String(10)  | Max 10 alphanumeric Digits  |

# Hotel descriptions

## Hotel - Fill descriptive text
> Request URL
```plaintext
availURL/get_hotel_descriptions.asp
```

> Request example
```plaintext
availURL/get_hotel_descriptions.asp?LangID=EN&Username=xmltestme&password=testme
```

> Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <LangID>EN</LangID>
    <Hotel Id="2" Name="Salmakis Beach Resort and Spa">
        <Description>
            <![CDATA[
            The Salmakis Beach Resort and Spa is set in the quieter part of Bodrum Bay and
            boasts impressive and varied Mediterranean architecture. Situated above a
            wonderful beach it also offers spectacular views across the bay to the harbor and
            castle of Bodrum. The resort includes 2 in-house restaurants, a 1500 m2 full service
            spa center, among other facilities and features. It is located only 1 km from the centre
            of Bodrum and 35 km from the Bodrum-Milas Airport.
            ]]>
        </Description>
        <Photos>
            <Photo>http://www.youhotels.com/photos/2/1.gif</Photo>
        </Photos>
    </Hotel>
```

**Request Parameters**

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| LangID  | String(2)  | EN  | EN: English  |
| Username  | Account Information  | String(15)  | Max 15 alphanumeric digits  |
| Password  | Account Information  | String(10)  | Max 10 alphanumeric digits  |

<br>

------------

<br>

**Response Parameters**

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Success  | Boolean  | True or False  | Clarifies if the request is successful  |
| Description | String |  | Detailed hotel description |
| Photos | String |  | Hotel thumbnail photo |

## Hotel List by Destination

> Request URL
```plaintext
availURL/get_hotel_list.asp
```

> Request example
```plaintext
availURL/get_hotel_list.asp?LangID=EN&username=xmltestme&password=testme
```

> Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <LangID>EN</LangID>
    <Country Code="DZ" Name="Algeria" ID="79">
        <Destination name="Algiers" ID="2989">
            <ISO_Codes Code_1="ALG" Code_2="" Code_3="" />
            <Resort ID="827">
                <Resort_Name>Algiers</Resort_Name>
                <Hotel>
                    <Hotel_ID>2200001202004</Hotel_ID>
                    <Hotel_Name>Hilton Alger hotel</Hotel_Name>
                    <Mapping>
                        <Latitude>36.738</Latitude>
                        <Longitude>3.1564</Longitude>
                    </Mapping>
                </Hotel>
            </Resort>
        </Destination>
    </Country>
    <Country Code="AD" Name="Andorra" ID="80">
        <Destination name="Andorra" ID="2760">
            <ISO_Codes Code_1="ALV" Code_2="" Code_3="" />
            <Resort ID="828">
                <Resort_Name>Arinsal</Resort_Name>
                <Hotel>
                    <Hotel_ID>9499</Hotel_ID>
                    <Hotel_Name>Husa Xalet Besoli</Hotel_Name>
                    <Mapping>
                        <Latitude>42.5682</Latitude>
                        <Longitude>1.4898</Longitude>
                    </Mapping>
                </Hotel>
                <Hotel>
                    <Hotel_ID>2200001204277</Hotel_ID>
                    <Hotel_Name>Husa Xalet Verdu</Hotel_Name>
                    <Mapping>
                        <Latitude>42.5682</Latitude>
                        <Longitude>1.4898</Longitude>
                    </Mapping>
                </Hotel>
            </Resort>
        </Destination>
    </Country>
</HtSearchRq>
```

**Request Parameters**

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| LangID  | String(2)  | EN  | EN: English  |
| Username  | Account Information  | String(15)  | Max 15 alphanumeric digits  |
| Password  | Account Information  | String(10)  | Max 10 alphanumeric digits  |

<br>

------------

<br>

**Response Parameters**

| Name  | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Success  | Boolean  | True or False  | Clarifies if the request is successful  |
| LangID  | String(2)  | EN  | EN: English  |
| Country_Code  | String  |   |   |
| Name  | String  |   |   |
| ISO_Codes  | String  | ISO  |   |
| Resort_ID  | Numeric  |   |   |
| Resort_Name | String | | |
| HID | Numeric(15) | | Max 15 Numeric Digits |
| Hotel_Name | String | | |
| Latitude | Numeric | | |
| Longitude | Numeric | | | |

# Booking list

## Booking List request
> Request URL
```plaintext
availURL/confirmations/get_agent_bookings.aspx
```

> Request example with booking reservation ID
```plaintext
availURL/confirmations/get_agent_bookings.aspx?LangID=EN&username=xmltestme&password=testme&Booking_ref=11303060006278815
```

> Request example with reservation date
```plaintext
availURL/confirmations/get_agent_bookings.aspx?LangID=EN&username=xmltestme&password=testme&res_from=01/03/2019&res_to=01/03/2019
```

>Response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>True</Success>
    <Handling_Agent>NEW</Handling_Agent>
    <Booking_info>
        <Booking ref="11303060006278815" Res_Date="06/03/2013" From_day="26/04/2013" To_day="30/04/2013" Num_of_ rooms="1" CountryCode="AE">
            <Client Title="Mrs" First_name="clare" Last_name="smith" />
            <Booking_Status>NEW</Booking_Status>
            <Conf_Status>UNCONF</Conf_Status>
            <Currency>GBP</Currency>
            <Exchange_rate>1.18</Exchange_rate>
            <Final_Rate>744.59</Final_Rate>
            <Hotel ID="6202" Name="Jebel Ali Hotel and Golf Resort">
                <GWGHotelID />
                <Hotel_Address>
                    <Address>Exit 13, Mina Jebel Ali | PO Box 9255</Address>
                    <Post_Code />
                    <City>Jumeirah Beach</City>
                    <Tel>0097 1444 73103</Tel>
                    <Fax>0097 1444 73105</Fax>
                </Hotel_Address>
                <Room ID="205536">
                    <RoomType>Twin/Double Room</RoomType>
                    <ViewType>Sea View</ViewType>
                    <IndexType>A</IndexType>
                    <GWGRoomType />
                    <board>AI</board>
                    <GuestCounts>
                        <GuestCount AgeQualifyingCode="10" Count="2" />
                    </GuestCounts>
                </Room>
                <Addons>
                    <Offers Gala_meal="0" Transfer="" Early_Booking_Discount="0" Free_Stay="1" Special_Offer="1" />
                </Addons>
                <Notes>
                    <Customer_Note>
                        <![CDATA[ ]]>
                    </Customer_Note>
                </Notes>
            </Hotel>
            <FlightDetails>
                <ArrivalInfo />
                <ArrivalAirportCode />
                <DepartureInfo />
                <DepartureAirportCode />
            </FlightDetails>
        </Booking>
    </Booking_info>
</HtSearchRq>
```
Retrieve the bookings made during a specific from-to period, or checking in on a specific from-to period, or retrieve/validate information regarding a specific booking.

<aside class="notice">
You would either use type1 request, where ResID (reservation id) need to be specified or you can use type2 request, where you provide Reservation date (at least one of from,to) or Checkin date (at least one of from,to)
</aside>

**Request Parameters**

| Name   | Type  | Format  | Comment  |
| ------------ | ------------ | ------------ | ------------ |
| Username  | String(15)   |   | Account info  |
| Password | String(10) | | Account info |
| chkin_from  | Date  | dd/mm/yyyy  | retrieve bookings with checkin >= chkin_from  |
| chkin_to | Date | dd/mm/yyyy | retreive bookings with checkin <= chkin_to |
| res_from | String(15) | dd/mm/yyyy | retreive bookings with reservation date >= res_from |
| res_to | String(10) | dd/mm/yyyy | retrieve bookings with reservation date <=res_to |
| Booking_ref | Numeric | | Retrieve booking detail given it’s Booking reference |

# Errors

This section highlights common error messages and possible solutions.

## Session Expired

> Session expired response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>False</Success>
    <ErrorMsg>Session Expired </ErrorMsg>
</HtSearchRq>
```

**Reason** - This error means same session ID is used for two different bookings. One session ID can be used for one booking only.
**Solution** - Use new session ID for every booking

## Rate difference

>Rate difference response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>False</Success>
    <ErrorMsg> Current rate for Room1_Rate is different than the original
search</ErrorMsg>
    <New_Rate>622.97</New_Rate>
</HtSearchRq>
```

**Reason** - Reason – Room price can change prior to the completion of booking. Therefore it is possible that during availability search system might show a different price but during booking process prices may change.
**Solution**  - Enter the new rate in the booking query

## Invalid account information

>Invalid account response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>False</Success>
    <ErrorMsg> Invalid account information</ErrorMsg>
</HtSearchRq>
```

**Reason** - Invalid username and password

## Not existing room

>Not existing room response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>False</Success>
    <ErrorMsg>The room does not exist or it doesn't belong to the specific hotel or
it cannot occupy the number of people</ErrorMsg>
</HtSearchRq>
```

**Reason** - The room is not anymore available in the hotel or particular room does not belong to the hotel or room cannot occupy the number of people. Sometime the availability search shows a particular room but the booking process might show the above error.

## Invalid IP

>Invalid IP Address response
```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<HtSearchRq>
    <Success>False</Success>
    <ErrorMsg>Invalid IP Address</ErrorMsg>
</HtSearchRq>
```

**Reason** - Your IPs are not whitelisted.
**Solution** - Please send us your known IP range and XML credentials to allow us to whitelist

## Already cancelled
>Booking is already cancelled response
```
<Success>False</Success>
<ErrorMsg>Booking Is Already Cancelled</ErrorMsg>
```

**Reason** - Attempting to cancel a booking that is already cancelled

## Other considerations
>No results request
```
<HtSearchRq>
<Success>False</Success>
<ErrorMsg>NO RESULTS FOUND</ErrorMsg>
</HtSearchRq>
```

If availability search does not return any results please check the following
- LangID
- Dstn, resort or hotel codes.
- HID
Incorrect codes will not show any results.

<aside class="notice">
We don't have any facility which displays whether the code is valid or not.
</aside>

No. of nights – Most of our properties work on more than 3 nights basis.
Therefore Nights=2 may not show any results.

## Full Error message table

- The session_ID is empty or not valid
- Session Expired
- Invalid number of Nights
- Customer_title cannot be empty
- Customer_firstname cannot be empty
- Customer_lastname cannot be empty
- Invalid number of Rooms
- Invalid Room1_Rate
- Invalid Room2_Rate
- Invalid Room3_Rate
- Invalid Checkin_Date
- Search is for past dates
- ADLTS_1 needs definition
- CHILD_1 needs definition
- Invalid RID
- ADLTS_2 needs definition
- CHILD_2 needs definition
- Invalid RID_2
- ADLTS_3 needs definition
- CHILD_3 needs definition
- Invalid RID_3
- Invalid child age range (proper age range should be 2-14 or -1 for infants)
- Child age cannot be blank
- Invalid HID
- No results found
- The hotel does not exist or it is not on sale
- The room does not exist or it doesn't belong to the specific hotel or it cannot occupy
- the number of people
- Room has no transfers
- This room cannot be booked
- Current rate for Room1_Rate is different than the original search
- Current rate for Room2_Rate is different than the original search
- Current rate for Room3_Rate is different than the original search
- The Arr_Date is not a valid date
- The Dep_Date is not a valid date
- The Arr_DepTime is not valid
- The Dep_DepTime is not valid
- The Arr_Flight_From is not valid
- The Arr_Flight_To is not valid
- The Dep_Flight_From is not valid
- The Transfer is not offered from Airport:
- The Transfer is not offered for Arrival date:
- The Transfer is not offered for Departure date:
- The Dep_Flight_To is not valid
- The Arr_Flight_Num is not valid
- The Dep_Flight_Num is not valid

# FAQ

## How to map

**Geo tree map**
 - Country > Destination > Resort > Hotel


**Mapping can be  done at**
- Destination level
- Resort level
- Hotel level
- Room type level (available for static content only)

## Recommended timeout settings

- Availability : 10 seconds
- Prebook : 60 seconds
- Booking : 60 seconds
- Get cancellation fees : 60 seconds
- Cancellation : 60 seconds
