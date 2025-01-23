# Get All Desktop Environments

Retrieves a list of all desktop environments available in the system, based on the list of operating systems considered as "desktop."

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/environments/desktop`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Response

{\`\[ { "environment\_id": 1, "name": "Windows 10", "type": "desktop", "os": "Windows", "version": "10", "enabled": true }, { "environment\_id": 2, "name": "macOS", "type": "desktop", "os": "macOS", "version": "Big Sur", "enabled": true }, { "environment\_id": 3, "name": "Ubuntu", "type": "desktop", "os": "Linux", "version": "20.04", "enabled": true } ]\`}

```
[
    {
        "operating_system": {
            "code": "WIN10",
            "platform": "Windows",
            "clean_name": "Windows 10",
            "screen_resolutions": [
                {
                    "resolution_name": "FHD",
                    "resolution_width": 1920,
                    "resolution_height": 1080
                },
                {
                    "resolution_name": "SVGA",
                    "resolution_width": 800,
                    "resolution_height": 600
                },
                {
                    "resolution_name": "SXGA",
                    "resolution_width": 1280,
                    "resolution_height": 1024
                },
                {
                    "resolution_name": "WXGA_P",
                    "resolution_width": 1440,
                    "resolution_height": 900
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 909,
                        "version": "dgdg",
                        "enabled": true
                    },
                    {
                        "environment_id": 1188,
                        "version": "134",
                        "enabled": true
                    },
                    {
                        "environment_id": 1193,
                        "version": "132",
                        "enabled": true
                    },
                    {
                        "environment_id": 1192,
                        "version": "131",
                        "enabled": true
                    },
                    {
                        "environment_id": 1191,
                        "version": "130",
                        "enabled": true
                    },
                    {
                        "environment_id": 1194,
                        "version": "129",
                        "enabled": true
                    },
                    {
                        "environment_id": 839,
                        "version": "101",
                        "enabled": true
                    },
                    {
                        "environment_id": 838,
                        "version": "100",
                        "enabled": true
                    },
                    {
                        "environment_id": 837,
                        "version": "99",
                        "enabled": true
                    },
                    {
                        "environment_id": 836,
                        "version": "98",
                        "enabled": true
                    },
                    {
                        "environment_id": 835,
                        "version": "97",
                        "enabled": true
                    },
                    {
                        "environment_id": 834,
                        "version": "96",
                        "enabled": true
                    },
                    {
                        "environment_id": 810,
                        "version": "95",
                        "enabled": true
                    },
                    {
                        "environment_id": 809,
                        "version": "94",
                        "enabled": true
                    },
                    {
                        "environment_id": 808,
                        "version": "93",
                        "enabled": true
                    },
                    {
                        "environment_id": 807,
                        "version": "92",
                        "enabled": true
                    },
                    {
                        "environment_id": 806,
                        "version": "91",
                        "enabled": true
                    },
                    {
                        "environment_id": 805,
                        "version": "90",
                        "enabled": true
                    },
                    {
                        "environment_id": 786,
                        "version": "89",
                        "enabled": true
                    },
                    {
                        "environment_id": 785,
                        "version": "88",
                        "enabled": true
                    },
                    {
                        "environment_id": 783,
                        "version": "87",
                        "enabled": true
                    },
                    {
                        "environment_id": 784,
                        "version": "86",
                        "enabled": true
                    },
                    {
                        "environment_id": 804,
                        "version": "85",
                        "enabled": true
                    },
                    {
                        "environment_id": 803,
                        "version": "84",
                        "enabled": true
                    },
                    {
                        "environment_id": 799,
                        "version": "79",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 948,
                        "version": "110.3",
                        "enabled": true
                    },
                    {
                        "environment_id": 968,
                        "version": "13.2",
                        "enabled": true
                    },
                    {
                        "environment_id": 1170,
                        "version": "13v5",
                        "enabled": true
                    },
                    {
                        "environment_id": 1168,
                        "version": "14v5",
                        "enabled": true
                    },
                    {
                        "environment_id": 956,
                        "version": "9.3.2",
                        "enabled": true
                    },
                    {
                        "environment_id": 713,
                        "version": "ADEYA",
                        "enabled": true
                    },
                    {
                        "environment_id": 1041,
                        "version": "deneme",
                        "enabled": true
                    },
                    {
                        "environment_id": 1166,
                        "version": "FURKAN",
                        "enabled": true
                    },
                    {
                        "environment_id": 440,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 1062,
                        "version": "Latesttt",
                        "enabled": true
                    },
                    {
                        "environment_id": 441,
                        "version": "PREVIOUS",
                        "enabled": true
                    },
                    {
                        "environment_id": 1178,
                        "version": "v103",
                        "enabled": true
                    },
                    {
                        "environment_id": 1182,
                        "version": "V127",
                        "enabled": true
                    },
                    {
                        "environment_id": 1179,
                        "version": "128",
                        "enabled": true
                    },
                    {
                        "environment_id": 1190,
                        "version": "118",
                        "enabled": true
                    },
                    {
                        "environment_id": 1189,
                        "version": "117",
                        "enabled": true
                    },
                    {
                        "environment_id": 1187,
                        "version": "116",
                        "enabled": true
                    },
                    {
                        "environment_id": 1186,
                        "version": "115",
                        "enabled": true
                    },
                    {
                        "environment_id": 1167,
                        "version": "110",
                        "enabled": true
                    },
                    {
                        "environment_id": 1169,
                        "version": "13",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": [
                    {
                        "environment_id": 665,
                        "version": "7",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": [
                    {
                        "environment_id": 589,
                        "version": "LATEST",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": [
                    {
                        "environment_id": 724,
                        "version": "LATEST",
                        "enabled": true
                    }
                ]
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "WIN11",
            "platform": "Windows",
            "clean_name": "Windows 11",
            "screen_resolutions": [],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": []
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": []
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": []
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": []
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "WIN8_1",
            "platform": "Windows",
            "clean_name": "Windows 8.1",
            "screen_resolutions": [
                {
                    "resolution_name": "SXGA",
                    "resolution_width": 1280,
                    "resolution_height": 1024
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 868,
                        "version": "101",
                        "enabled": true
                    },
                    {
                        "environment_id": 867,
                        "version": "100",
                        "enabled": true
                    },
                    {
                        "environment_id": 866,
                        "version": "99",
                        "enabled": true
                    },
                    {
                        "environment_id": 865,
                        "version": "98",
                        "enabled": true
                    },
                    {
                        "environment_id": 864,
                        "version": "97",
                        "enabled": true
                    },
                    {
                        "environment_id": 863,
                        "version": "96",
                        "enabled": true
                    },
                    {
                        "environment_id": 862,
                        "version": "95",
                        "enabled": true
                    },
                    {
                        "environment_id": 861,
                        "version": "94",
                        "enabled": true
                    },
                    {
                        "environment_id": 860,
                        "version": "93",
                        "enabled": true
                    },
                    {
                        "environment_id": 859,
                        "version": "92",
                        "enabled": true
                    },
                    {
                        "environment_id": 869,
                        "version": "91",
                        "enabled": true
                    },
                    {
                        "environment_id": 858,
                        "version": "90",
                        "enabled": true
                    },
                    {
                        "environment_id": 782,
                        "version": "81",
                        "enabled": true
                    },
                    {
                        "environment_id": 781,
                        "version": "80",
                        "enabled": true
                    },
                    {
                        "environment_id": 780,
                        "version": "79",
                        "enabled": true
                    },
                    {
                        "environment_id": 778,
                        "version": "77",
                        "enabled": true
                    },
                    {
                        "environment_id": 777,
                        "version": "76",
                        "enabled": true
                    },
                    {
                        "environment_id": 776,
                        "version": "75",
                        "enabled": true
                    },
                    {
                        "environment_id": 764,
                        "version": "72",
                        "enabled": true
                    },
                    {
                        "environment_id": 763,
                        "version": "71",
                        "enabled": true
                    },
                    {
                        "environment_id": 747,
                        "version": "70",
                        "enabled": true
                    },
                    {
                        "environment_id": 746,
                        "version": "69",
                        "enabled": true
                    },
                    {
                        "environment_id": 735,
                        "version": "68",
                        "enabled": true
                    },
                    {
                        "environment_id": 734,
                        "version": "67",
                        "enabled": true
                    },
                    {
                        "environment_id": 717,
                        "version": "66",
                        "enabled": true
                    },
                    {
                        "environment_id": 707,
                        "version": "65",
                        "enabled": true
                    },
                    {
                        "environment_id": 696,
                        "version": "64",
                        "enabled": true
                    },
                    {
                        "environment_id": 695,
                        "version": "63",
                        "enabled": true
                    },
                    {
                        "environment_id": 625,
                        "version": "60",
                        "enabled": true
                    },
                    {
                        "environment_id": 624,
                        "version": "59",
                        "enabled": true
                    },
                    {
                        "environment_id": 623,
                        "version": "58",
                        "enabled": true
                    },
                    {
                        "environment_id": 593,
                        "version": "57",
                        "enabled": true
                    },
                    {
                        "environment_id": 592,
                        "version": "56",
                        "enabled": true
                    },
                    {
                        "environment_id": 591,
                        "version": "55",
                        "enabled": true
                    },
                    {
                        "environment_id": 590,
                        "version": "54",
                        "enabled": true
                    },
                    {
                        "environment_id": 316,
                        "version": "47",
                        "enabled": true
                    },
                    {
                        "environment_id": 315,
                        "version": "46",
                        "enabled": true
                    },
                    {
                        "environment_id": 292,
                        "version": "45",
                        "enabled": true
                    },
                    {
                        "environment_id": 291,
                        "version": "44",
                        "enabled": true
                    },
                    {
                        "environment_id": 290,
                        "version": "43",
                        "enabled": true
                    },
                    {
                        "environment_id": 289,
                        "version": "42",
                        "enabled": true
                    },
                    {
                        "environment_id": 288,
                        "version": "41",
                        "enabled": true
                    },
                    {
                        "environment_id": 227,
                        "version": "40",
                        "enabled": true
                    },
                    {
                        "environment_id": 226,
                        "version": "39",
                        "enabled": true
                    },
                    {
                        "environment_id": 225,
                        "version": "38",
                        "enabled": true
                    },
                    {
                        "environment_id": 224,
                        "version": "37",
                        "enabled": true
                    },
                    {
                        "environment_id": 198,
                        "version": "36",
                        "enabled": true
                    },
                    {
                        "environment_id": 197,
                        "version": "35",
                        "enabled": true
                    },
                    {
                        "environment_id": 156,
                        "version": "34",
                        "enabled": true
                    },
                    {
                        "environment_id": 155,
                        "version": "33",
                        "enabled": true
                    },
                    {
                        "environment_id": 102,
                        "version": "32",
                        "enabled": true
                    },
                    {
                        "environment_id": 101,
                        "version": "31",
                        "enabled": true
                    },
                    {
                        "environment_id": 100,
                        "version": "30",
                        "enabled": true
                    },
                    {
                        "environment_id": 99,
                        "version": "29",
                        "enabled": true
                    },
                    {
                        "environment_id": 97,
                        "version": "28",
                        "enabled": true
                    },
                    {
                        "environment_id": 96,
                        "version": "27",
                        "enabled": true
                    },
                    {
                        "environment_id": 95,
                        "version": "26",
                        "enabled": true
                    },
                    {
                        "environment_id": 94,
                        "version": "25",
                        "enabled": true
                    },
                    {
                        "environment_id": 93,
                        "version": "24",
                        "enabled": true
                    },
                    {
                        "environment_id": 92,
                        "version": "23",
                        "enabled": true
                    },
                    {
                        "environment_id": 91,
                        "version": "22",
                        "enabled": true
                    },
                    {
                        "environment_id": 90,
                        "version": "21",
                        "enabled": true
                    },
                    {
                        "environment_id": 89,
                        "version": "20",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 228,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 343,
                        "version": "PREVIOUS",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": []
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": [
                    {
                        "environment_id": 320,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 344,
                        "version": "PREVIOUS",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "WIN8",
            "platform": "Windows",
            "clean_name": "Windows 8",
            "screen_resolutions": [
                {
                    "resolution_name": "SXGA",
                    "resolution_width": 1280,
                    "resolution_height": 1024
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 348,
                        "version": "firefoxWin10",
                        "enabled": true
                    },
                    {
                        "environment_id": 845,
                        "version": "101",
                        "enabled": true
                    },
                    {
                        "environment_id": 844,
                        "version": "100",
                        "enabled": true
                    },
                    {
                        "environment_id": 843,
                        "version": "99",
                        "enabled": true
                    },
                    {
                        "environment_id": 842,
                        "version": "98",
                        "enabled": true
                    },
                    {
                        "environment_id": 841,
                        "version": "97",
                        "enabled": true
                    },
                    {
                        "environment_id": 840,
                        "version": "96",
                        "enabled": true
                    },
                    {
                        "environment_id": 846,
                        "version": "95",
                        "enabled": true
                    },
                    {
                        "environment_id": 847,
                        "version": "94",
                        "enabled": true
                    },
                    {
                        "environment_id": 848,
                        "version": "93",
                        "enabled": true
                    },
                    {
                        "environment_id": 849,
                        "version": "92",
                        "enabled": true
                    },
                    {
                        "environment_id": 850,
                        "version": "91",
                        "enabled": true
                    },
                    {
                        "environment_id": 851,
                        "version": "90",
                        "enabled": true
                    },
                    {
                        "environment_id": 852,
                        "version": "89",
                        "enabled": true
                    },
                    {
                        "environment_id": 857,
                        "version": "88",
                        "enabled": true
                    },
                    {
                        "environment_id": 856,
                        "version": "87",
                        "enabled": true
                    },
                    {
                        "environment_id": 855,
                        "version": "86",
                        "enabled": true
                    },
                    {
                        "environment_id": 853,
                        "version": "85",
                        "enabled": true
                    },
                    {
                        "environment_id": 854,
                        "version": "84",
                        "enabled": true
                    },
                    {
                        "environment_id": 775,
                        "version": "77",
                        "enabled": true
                    },
                    {
                        "environment_id": 774,
                        "version": "76",
                        "enabled": true
                    },
                    {
                        "environment_id": 773,
                        "version": "75",
                        "enabled": true
                    },
                    {
                        "environment_id": 762,
                        "version": "72",
                        "enabled": true
                    },
                    {
                        "environment_id": 761,
                        "version": "71",
                        "enabled": true
                    },
                    {
                        "environment_id": 745,
                        "version": "70",
                        "enabled": true
                    },
                    {
                        "environment_id": 744,
                        "version": "69",
                        "enabled": true
                    },
                    {
                        "environment_id": 737,
                        "version": "68",
                        "enabled": true
                    },
                    {
                        "environment_id": 736,
                        "version": "67",
                        "enabled": true
                    },
                    {
                        "environment_id": 726,
                        "version": "66",
                        "enabled": true
                    },
                    {
                        "environment_id": 725,
                        "version": "65",
                        "enabled": true
                    },
                    {
                        "environment_id": 690,
                        "version": "64",
                        "enabled": true
                    },
                    {
                        "environment_id": 688,
                        "version": "63",
                        "enabled": true
                    },
                    {
                        "environment_id": 689,
                        "version": "62",
                        "enabled": true
                    },
                    {
                        "environment_id": 621,
                        "version": "60",
                        "enabled": true
                    },
                    {
                        "environment_id": 620,
                        "version": "59",
                        "enabled": true
                    },
                    {
                        "environment_id": 619,
                        "version": "58",
                        "enabled": true
                    },
                    {
                        "environment_id": 587,
                        "version": "57",
                        "enabled": true
                    },
                    {
                        "environment_id": 586,
                        "version": "56",
                        "enabled": true
                    },
                    {
                        "environment_id": 585,
                        "version": "55",
                        "enabled": true
                    },
                    {
                        "environment_id": 584,
                        "version": "54",
                        "enabled": true
                    },
                    {
                        "environment_id": 622,
                        "version": "50",
                        "enabled": true
                    },
                    {
                        "environment_id": 322,
                        "version": "47",
                        "enabled": true
                    },
                    {
                        "environment_id": 321,
                        "version": "46",
                        "enabled": true
                    },
                    {
                        "environment_id": 297,
                        "version": "45",
                        "enabled": true
                    },
                    {
                        "environment_id": 296,
                        "version": "44",
                        "enabled": true
                    },
                    {
                        "environment_id": 295,
                        "version": "43",
                        "enabled": true
                    },
                    {
                        "environment_id": 294,
                        "version": "42",
                        "enabled": true
                    },
                    {
                        "environment_id": 293,
                        "version": "41",
                        "enabled": true
                    },
                    {
                        "environment_id": 222,
                        "version": "40",
                        "enabled": true
                    },
                    {
                        "environment_id": 221,
                        "version": "39",
                        "enabled": true
                    },
                    {
                        "environment_id": 220,
                        "version": "38",
                        "enabled": true
                    },
                    {
                        "environment_id": 219,
                        "version": "37",
                        "enabled": true
                    },
                    {
                        "environment_id": 194,
                        "version": "36",
                        "enabled": true
                    },
                    {
                        "environment_id": 193,
                        "version": "35",
                        "enabled": true
                    },
                    {
                        "environment_id": 81,
                        "version": "33",
                        "enabled": true
                    },
                    {
                        "environment_id": 80,
                        "version": "32",
                        "enabled": true
                    },
                    {
                        "environment_id": 79,
                        "version": "31",
                        "enabled": true
                    },
                    {
                        "environment_id": 78,
                        "version": "30",
                        "enabled": true
                    },
                    {
                        "environment_id": 77,
                        "version": "29",
                        "enabled": true
                    },
                    {
                        "environment_id": 63,
                        "version": "28",
                        "enabled": true
                    },
                    {
                        "environment_id": 61,
                        "version": "27",
                        "enabled": true
                    },
                    {
                        "environment_id": 2,
                        "version": "26",
                        "enabled": true
                    },
                    {
                        "environment_id": 84,
                        "version": "26",
                        "enabled": true
                    },
                    {
                        "environment_id": 60,
                        "version": "25",
                        "enabled": true
                    },
                    {
                        "environment_id": 59,
                        "version": "24",
                        "enabled": true
                    },
                    {
                        "environment_id": 58,
                        "version": "23",
                        "enabled": true
                    },
                    {
                        "environment_id": 57,
                        "version": "22",
                        "enabled": true
                    },
                    {
                        "environment_id": 56,
                        "version": "21",
                        "enabled": true
                    },
                    {
                        "environment_id": 55,
                        "version": "20",
                        "enabled": true
                    },
                    {
                        "environment_id": 82,
                        "version": "20",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 347,
                        "version": "chromeWin10",
                        "enabled": true
                    },
                    {
                        "environment_id": 223,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 336,
                        "version": "PREVIOUS",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": []
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": [
                    {
                        "environment_id": 908,
                        "version": "0.10.0",
                        "enabled": true
                    },
                    {
                        "environment_id": 323,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 337,
                        "version": "PREVIOUS",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "VISTA",
            "platform": "Windows",
            "clean_name": "Windows 7",
            "screen_resolutions": [
                {
                    "resolution_name": "SXGA",
                    "resolution_width": 1280,
                    "resolution_height": 1024
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 772,
                        "version": "77",
                        "enabled": true
                    },
                    {
                        "environment_id": 771,
                        "version": "76",
                        "enabled": true
                    },
                    {
                        "environment_id": 770,
                        "version": "75",
                        "enabled": true
                    },
                    {
                        "environment_id": 758,
                        "version": "72",
                        "enabled": true
                    },
                    {
                        "environment_id": 757,
                        "version": "71",
                        "enabled": true
                    },
                    {
                        "environment_id": 743,
                        "version": "70",
                        "enabled": true
                    },
                    {
                        "environment_id": 742,
                        "version": "69",
                        "enabled": true
                    },
                    {
                        "environment_id": 733,
                        "version": "68",
                        "enabled": true
                    },
                    {
                        "environment_id": 716,
                        "version": "66",
                        "enabled": true
                    },
                    {
                        "environment_id": 715,
                        "version": "65",
                        "enabled": true
                    },
                    {
                        "environment_id": 693,
                        "version": "64",
                        "enabled": true
                    },
                    {
                        "environment_id": 692,
                        "version": "63",
                        "enabled": true
                    },
                    {
                        "environment_id": 691,
                        "version": "62",
                        "enabled": true
                    },
                    {
                        "environment_id": 631,
                        "version": "60",
                        "enabled": true
                    },
                    {
                        "environment_id": 630,
                        "version": "59",
                        "enabled": true
                    },
                    {
                        "environment_id": 629,
                        "version": "58",
                        "enabled": true
                    },
                    {
                        "environment_id": 579,
                        "version": "57",
                        "enabled": true
                    },
                    {
                        "environment_id": 580,
                        "version": "56",
                        "enabled": true
                    },
                    {
                        "environment_id": 581,
                        "version": "55",
                        "enabled": true
                    },
                    {
                        "environment_id": 582,
                        "version": "54",
                        "enabled": true
                    },
                    {
                        "environment_id": 339,
                        "version": "47",
                        "enabled": true
                    },
                    {
                        "environment_id": 338,
                        "version": "46",
                        "enabled": true
                    },
                    {
                        "environment_id": 287,
                        "version": "45",
                        "enabled": true
                    },
                    {
                        "environment_id": 286,
                        "version": "44",
                        "enabled": true
                    },
                    {
                        "environment_id": 285,
                        "version": "43",
                        "enabled": true
                    },
                    {
                        "environment_id": 284,
                        "version": "42",
                        "enabled": true
                    },
                    {
                        "environment_id": 283,
                        "version": "41",
                        "enabled": true
                    },
                    {
                        "environment_id": 217,
                        "version": "40",
                        "enabled": true
                    },
                    {
                        "environment_id": 216,
                        "version": "39",
                        "enabled": true
                    },
                    {
                        "environment_id": 215,
                        "version": "38",
                        "enabled": true
                    },
                    {
                        "environment_id": 214,
                        "version": "37",
                        "enabled": true
                    },
                    {
                        "environment_id": 190,
                        "version": "36",
                        "enabled": true
                    },
                    {
                        "environment_id": 189,
                        "version": "35",
                        "enabled": true
                    },
                    {
                        "environment_id": 182,
                        "version": "34",
                        "enabled": true
                    },
                    {
                        "environment_id": 180,
                        "version": "33",
                        "enabled": true
                    },
                    {
                        "environment_id": 179,
                        "version": "32",
                        "enabled": true
                    },
                    {
                        "environment_id": 178,
                        "version": "31",
                        "enabled": true
                    },
                    {
                        "environment_id": 177,
                        "version": "30",
                        "enabled": true
                    },
                    {
                        "environment_id": 176,
                        "version": "29",
                        "enabled": true
                    },
                    {
                        "environment_id": 175,
                        "version": "28",
                        "enabled": true
                    },
                    {
                        "environment_id": 174,
                        "version": "27",
                        "enabled": true
                    },
                    {
                        "environment_id": 173,
                        "version": "26",
                        "enabled": true
                    },
                    {
                        "environment_id": 172,
                        "version": "25",
                        "enabled": true
                    },
                    {
                        "environment_id": 171,
                        "version": "24",
                        "enabled": true
                    },
                    {
                        "environment_id": 170,
                        "version": "23",
                        "enabled": true
                    },
                    {
                        "environment_id": 169,
                        "version": "22",
                        "enabled": true
                    },
                    {
                        "environment_id": 168,
                        "version": "21",
                        "enabled": true
                    },
                    {
                        "environment_id": 66,
                        "version": "20",
                        "enabled": true
                    },
                    {
                        "environment_id": 128,
                        "version": "13",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 218,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 406,
                        "version": "OLDER",
                        "enabled": true
                    },
                    {
                        "environment_id": 340,
                        "version": "PREVIOUS",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": []
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": [
                    {
                        "environment_id": 342,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 341,
                        "version": "PREVIOUS",
                        "enabled": true
                    },
                    {
                        "environment_id": 603,
                        "version": "49",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "XP",
            "platform": "Windows",
            "clean_name": "Windows XP",
            "screen_resolutions": [
                {
                    "resolution_name": "FHD",
                    "resolution_width": 1920,
                    "resolution_height": 1080
                },
                {
                    "resolution_name": "SXGA",
                    "resolution_width": 1280,
                    "resolution_height": 1024
                },
                {
                    "resolution_name": "WXGA",
                    "resolution_width": 1280,
                    "resolution_height": 800
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 302,
                        "version": "45",
                        "enabled": true
                    },
                    {
                        "environment_id": 301,
                        "version": "44",
                        "enabled": true
                    },
                    {
                        "environment_id": 300,
                        "version": "43",
                        "enabled": true
                    },
                    {
                        "environment_id": 299,
                        "version": "42",
                        "enabled": true
                    },
                    {
                        "environment_id": 458,
                        "version": "41",
                        "enabled": true
                    },
                    {
                        "environment_id": 212,
                        "version": "40",
                        "enabled": true
                    },
                    {
                        "environment_id": 211,
                        "version": "39",
                        "enabled": true
                    },
                    {
                        "environment_id": 210,
                        "version": "38",
                        "enabled": true
                    },
                    {
                        "environment_id": 209,
                        "version": "37",
                        "enabled": true
                    },
                    {
                        "environment_id": 203,
                        "version": "36",
                        "enabled": true
                    },
                    {
                        "environment_id": 202,
                        "version": "35",
                        "enabled": true
                    },
                    {
                        "environment_id": 161,
                        "version": "34",
                        "enabled": true
                    },
                    {
                        "environment_id": 160,
                        "version": "33",
                        "enabled": true
                    },
                    {
                        "environment_id": 147,
                        "version": "32",
                        "enabled": true
                    },
                    {
                        "environment_id": 146,
                        "version": "31",
                        "enabled": true
                    },
                    {
                        "environment_id": 145,
                        "version": "30",
                        "enabled": true
                    },
                    {
                        "environment_id": 144,
                        "version": "29",
                        "enabled": true
                    },
                    {
                        "environment_id": 143,
                        "version": "28",
                        "enabled": true
                    },
                    {
                        "environment_id": 142,
                        "version": "27",
                        "enabled": true
                    },
                    {
                        "environment_id": 141,
                        "version": "26",
                        "enabled": true
                    },
                    {
                        "environment_id": 140,
                        "version": "25",
                        "enabled": true
                    },
                    {
                        "environment_id": 139,
                        "version": "24",
                        "enabled": true
                    },
                    {
                        "environment_id": 138,
                        "version": "23",
                        "enabled": true
                    },
                    {
                        "environment_id": 137,
                        "version": "22",
                        "enabled": true
                    },
                    {
                        "environment_id": 136,
                        "version": "21",
                        "enabled": true
                    },
                    {
                        "environment_id": 135,
                        "version": "20",
                        "enabled": true
                    },
                    {
                        "environment_id": 134,
                        "version": "19",
                        "enabled": true
                    },
                    {
                        "environment_id": 133,
                        "version": "18",
                        "enabled": true
                    },
                    {
                        "environment_id": 132,
                        "version": "17",
                        "enabled": true
                    },
                    {
                        "environment_id": 131,
                        "version": "16",
                        "enabled": true
                    },
                    {
                        "environment_id": 130,
                        "version": "15",
                        "enabled": true
                    },
                    {
                        "environment_id": 129,
                        "version": "14",
                        "enabled": true
                    },
                    {
                        "environment_id": 127,
                        "version": "12",
                        "enabled": true
                    },
                    {
                        "environment_id": 126,
                        "version": "11",
                        "enabled": true
                    },
                    {
                        "environment_id": 17,
                        "version": "10",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 651,
                        "version": "12",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": []
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": []
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "LINUX",
            "platform": "Linux",
            "clean_name": "Linux",
            "screen_resolutions": [
                {
                    "resolution_name": "HD",
                    "resolution_width": 1366,
                    "resolution_height": 768
                },
                {
                    "resolution_name": "SVGA",
                    "resolution_width": 800,
                    "resolution_height": 600
                },
                {
                    "resolution_name": "SXGA",
                    "resolution_width": 1280,
                    "resolution_height": 1024
                },
                {
                    "resolution_name": "WXGA",
                    "resolution_width": 1280,
                    "resolution_height": 800
                },
                {
                    "resolution_name": "WXGA_P",
                    "resolution_width": 1440,
                    "resolution_height": 900
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 833,
                        "version": "101",
                        "enabled": true
                    },
                    {
                        "environment_id": 832,
                        "version": "100",
                        "enabled": true
                    },
                    {
                        "environment_id": 831,
                        "version": "99",
                        "enabled": true
                    },
                    {
                        "environment_id": 830,
                        "version": "98",
                        "enabled": true
                    },
                    {
                        "environment_id": 829,
                        "version": "97",
                        "enabled": true
                    },
                    {
                        "environment_id": 828,
                        "version": "96",
                        "enabled": true
                    },
                    {
                        "environment_id": 827,
                        "version": "95",
                        "enabled": true
                    },
                    {
                        "environment_id": 826,
                        "version": "94",
                        "enabled": true
                    },
                    {
                        "environment_id": 825,
                        "version": "93",
                        "enabled": true
                    },
                    {
                        "environment_id": 824,
                        "version": "92",
                        "enabled": true
                    },
                    {
                        "environment_id": 823,
                        "version": "91",
                        "enabled": true
                    },
                    {
                        "environment_id": 822,
                        "version": "90",
                        "enabled": true
                    },
                    {
                        "environment_id": 821,
                        "version": "89",
                        "enabled": true
                    },
                    {
                        "environment_id": 820,
                        "version": "88",
                        "enabled": true
                    },
                    {
                        "environment_id": 819,
                        "version": "87",
                        "enabled": true
                    },
                    {
                        "environment_id": 818,
                        "version": "86",
                        "enabled": true
                    },
                    {
                        "environment_id": 817,
                        "version": "85",
                        "enabled": true
                    },
                    {
                        "environment_id": 816,
                        "version": "84",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 768,
                        "version": "76denee",
                        "enabled": true
                    },
                    {
                        "environment_id": 235,
                        "version": "LATEST",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": []
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": []
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "MAC",
            "platform": "Mac",
            "clean_name": "Mac",
            "screen_resolutions": [
                {
                    "resolution_name": "FHD",
                    "resolution_width": 1920,
                    "resolution_height": 1080
                },
                {
                    "resolution_name": "HD",
                    "resolution_width": 1366,
                    "resolution_height": 768
                },
                {
                    "resolution_name": "WXGA_P",
                    "resolution_width": 1440,
                    "resolution_height": 900
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": false
        },
        "manufacturers": [],
        "browsers": [
            {
                "code": "firefox",
                "browser_name": "Firefox",
                "name": "FIREFOX",
                "details": [
                    {
                        "environment_id": 432,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 434,
                        "version": "PREVIOUS",
                        "enabled": true
                    },
                    {
                        "environment_id": 598,
                        "version": "57",
                        "enabled": true
                    },
                    {
                        "environment_id": 346,
                        "version": "47",
                        "enabled": true
                    },
                    {
                        "environment_id": 314,
                        "version": "45",
                        "enabled": true
                    },
                    {
                        "environment_id": 162,
                        "version": "34",
                        "enabled": true
                    },
                    {
                        "environment_id": 148,
                        "version": "33",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "chrome",
                "browser_name": "Chrome",
                "name": "CHROME",
                "details": [
                    {
                        "environment_id": 714,
                        "version": "ADEYA",
                        "enabled": true
                    },
                    {
                        "environment_id": 308,
                        "version": "LATEST",
                        "enabled": true
                    },
                    {
                        "environment_id": 435,
                        "version": "PREVIOUS",
                        "enabled": true
                    },
                    {
                        "environment_id": 1195,
                        "version": "131",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "internet explorer",
                "browser_name": "Internet Explorer",
                "name": "IE",
                "details": []
            },
            {
                "code": "safari",
                "browser_name": "Safari",
                "name": "SAFARI",
                "details": [
                    {
                        "environment_id": 1185,
                        "version": "17",
                        "enabled": true
                    },
                    {
                        "environment_id": 1183,
                        "version": "16",
                        "enabled": true
                    },
                    {
                        "environment_id": 1184,
                        "version": "15",
                        "enabled": true
                    },
                    {
                        "environment_id": 723,
                        "version": "11",
                        "enabled": true
                    },
                    {
                        "environment_id": 583,
                        "version": "10",
                        "enabled": true
                    },
                    {
                        "environment_id": 335,
                        "version": "10",
                        "enabled": true
                    },
                    {
                        "environment_id": 306,
                        "version": "9",
                        "enabled": true
                    },
                    {
                        "environment_id": 150,
                        "version": "7",
                        "enabled": true
                    },
                    {
                        "environment_id": 6,
                        "version": "6",
                        "enabled": true
                    },
                    {
                        "environment_id": 661,
                        "version": "2",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "operablink",
                "browser_name": "Opera",
                "name": "OPERA",
                "details": [
                    {
                        "environment_id": 722,
                        "version": "LATEST",
                        "enabled": true
                    }
                ]
            },
            {
                "code": "MicrosoftEdge",
                "browser_name": "Microsoft Edge",
                "name": "EDGE",
                "details": []
            }
        ],
        "enabled": false
    }
]
```

***

#### Key Response Fields

| Field            | Type      | Description                                                     |
| ---------------- | --------- | --------------------------------------------------------------- |
| `environment_id` | `Long`    | The unique identifier of the environment.                       |
| `name`           | `String`  | The name of the operating system (e.g., Windows 10, macOS).     |
| `type`           | `String`  | The type of the environment (always "desktop" in this case).    |
| `os`             | `String`  | The operating system name (e.g., Windows, macOS, Linux).        |
| `version`        | `String`  | The version of the operating system (e.g., 10, Big Sur, 20.04). |
| `enabled`        | `Boolean` | Indicates whether the environment is enabled for use.           |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/environments/desktop" \
--header 'Authorization: Bearer <your_access_token>'
```
