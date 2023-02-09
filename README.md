1. Open Postman
2. Create a Post/get Request
3. From Authorization folder choose OAUTh 2.0
4. Autenticate with user owner and password
5. Click on use token

Example of GET requests
List Agents
This is an example of list agentes
GET https://global-dialogflow.googleapis.com/v3/projects/hospitality-demo-361210/locations/global/agents/




Example of POST Request

Agent Intents belongs to sessions
POSR https://cloud.google.com/dialogflow/cx/docs/reference/rest/v3/projects.locations.agents.environments.sessions


```json
{
  "queryInput": {
    "text": {
      "text": "HELLO"
    },
    "languageCode": "en"
  },
  "queryParams": {
    "timeZone": "America/Los_Angeles"
  }
}
```

Answer
```json
{
    "responseId": "ea71d3ac-e776-4468-8beb-84ae94539cf4",
    "queryResult": {
        "text": "Hello",
        "languageCode": "en",
        "parameters": {
            "last_name": null,
            "channel": "chat",
            "customerverified": "not-set"
        },
        "responseMessages": [
            {
                "text": {
                    "text": [
                        "Hello! How can I help you?"
                    ]
                }
            },
            {
                "payload": {}
            },
            {}
        ],
        "webhookPayloads": [
            {}
        ],
        "currentPage": {
            "name": "projects/hospitality-demo-361210/locations/global/agents/fcb0a3b6-8299-4a9d-87e0-3731db89eab2/flows/00000000-0000-0000-0000-000000000000/pages/START_PAGE",
            "displayName": "Start Page"
        },
        "intent": {
            "name": "projects/hospitality-demo-361210/locations/global/agents/fcb0a3b6-8299-4a9d-87e0-3731db89eab2/intents/00000000-0000-0000-0000-000000000000",
            "displayName": "Default Welcome Intent"
        },
        "intentDetectionConfidence": 1,
        "diagnosticInfo": {
            "Session Id": "12345678",
            "Execution Sequence": [
                {
                    "Step 1": {
                        "InitialState": {
                            "FlowState": {
                                "FlowId": "00000000-0000-0000-0000-000000000000",
                                "Name": "Default Start Flow",
                                "PageState": {
                                    "PageId": "START_PAGE",
                                    "Name": "Start Page",
                                    "Status": "TRANSITION_ROUTING"
                                },
                                "Version": 0
                            },
                            "MatchedIntent": {
                                "Id": "00000000-0000-0000-0000-000000000000",
                                "Type": "NLU",
                                "Active": true,
                                "Score": 1,
                                "DisplayName": "Default Welcome Intent"
                            },
                            "SessionParameters": {
                                "channel": "chat",
                                "customerverified": "not-set",
                                "last_name": null
                            }
                        },
                        "Type": "INITIAL_STATE"
                    }
                },
                {
                    "Step 2": {
                        "Type": "STATE_MACHINE",
                        "StateMachine": {
                            "TriggeredIntent": "Default Welcome Intent",
                            "FlowLevelTransition": true,
                            "TriggeredCondition": "true",
                            "FlowState": {
                                "Version": 0,
                                "FlowId": "00000000-0000-0000-0000-000000000000",
                                "PageState": {
                                    "Status": "TRANSITION_ROUTING",
                                    "Name": "Start Page",
                                    "PageId": "START_PAGE"
                                },
                                "Name": "Default Start Flow"
                            },
                            "TriggeredTransitionRouteId": "aedea5a9-9b3a-43c3-8206-c89685bf415c",
                            "TargetPage": "abbd0d46-a3d3-41ee-acb2-04fbd2ec535f"
                        },
                        "FunctionExecution": {
                            "Responses": [
                                {
                                    "responseType": "HANDLER_PROMPT",
                                    "source": "VIRTUAL_AGENT",
                                    "text": {
                                        "text": [
                                            "Hello! How can I help you?"
                                        ],
                                        "redactedText": [
                                            "Hello! How can I help you?"
                                        ]
                                    }
                                },
                                {
                                    "payload": {},
                                    "responseType": "HANDLER_PROMPT",
                                    "source": "VIRTUAL_AGENT"
                                }
                            ]
                        }
                    }
                },
                {
                    "Step 3": {
                        "FunctionExecution": {
                            "Responses": [
                                {
                                    "responseType": "HANDLER_PROMPT",
                                    "text": {
                                        "redactedText": [
                                            "Hello! How can I help you?"
                                        ],
                                        "text": [
                                            "Hello! How can I help you?"
                                        ]
                                    },
                                    "source": "VIRTUAL_AGENT"
                                },
                                {
                                    "responseType": "HANDLER_PROMPT",
                                    "payload": {},
                                    "source": "VIRTUAL_AGENT"
                                }
                            ],
                            "Webhook": {
                                "Latency": "67 ms",
                                "Unauthorized FulfillmentResponse": false,
                                "URL": "https://us-central1-hospitality-demo-361210.cloudfunctions.net/dialogflow-main-wh",
                                "Status": "OK"
                            }
                        },
                        "StateMachine": {
                            "FlowState": {
                                "FlowId": "00000000-0000-0000-0000-000000000000",
                                "Name": "Default Start Flow",
                                "PageState": {
                                    "PageId": "abbd0d46-a3d3-41ee-acb2-04fbd2ec535f",
                                    "Name": "Check Channel",
                                    "Status": "ENTERING_PAGE"
                                },
                                "Version": 0
                            }
                        },
                        "Type": "STATE_MACHINE"
                    }
                },
                {
                    "Step 4": {
                        "StateMachine": {
                            "FlowState": {
                                "FlowId": "00000000-0000-0000-0000-000000000000",
                                "Version": 0,
                                "PageState": {
                                    "Status": "TRANSITION_ROUTING",
                                    "Name": "Check Channel",
                                    "PageId": "abbd0d46-a3d3-41ee-acb2-04fbd2ec535f",
                                    "FormFilled": true
                                },
                                "Name": "Default Start Flow"
                            },
                            "TargetPage": "START_PAGE",
                            "TriggeredTransitionRouteId": "978d2fbb-5dca-4b55-9131-fd3e38c708b5",
                            "TriggeredCondition": "$session.params.channel = chat"
                        },
                        "Type": "STATE_MACHINE",
                        "FunctionExecution": {
                            "Responses": [
                                {
                                    "responseType": "HANDLER_PROMPT",
                                    "text": {
                                        "redactedText": [
                                            "Hello! How can I help you?"
                                        ],
                                        "text": [
                                            "Hello! How can I help you?"
                                        ]
                                    },
                                    "source": "VIRTUAL_AGENT"
                                },
                                {
                                    "payload": {},
                                    "responseType": "HANDLER_PROMPT",
                                    "source": "VIRTUAL_AGENT"
                                }
                            ]
                        }
                    }
                },
                {
                    "Step 5": {
                        "Type": "STATE_MACHINE",
                        "StateMachine": {
                            "FlowState": {
                                "Version": 0,
                                "PageState": {
                                    "PageId": "START_PAGE",
                                    "Name": "Start Page",
                                    "Status": "TRANSITION_ROUTING"
                                },
                                "Name": "Default Start Flow",
                                "FlowId": "00000000-0000-0000-0000-000000000000"
                            }
                        }
                    }
                }
            ],
            "Webhook Latencies (ms)": [
                67
            ],
            "Alternative Matched Intents": [
                {
                    "DisplayName": "Default Welcome Intent",
                    "Type": "NLU",
                    "Active": true,
                    "Id": "00000000-0000-0000-0000-000000000000",
                    "Score": 1
                }
            ],
            "Transition Targets Chain": [
                {
                    "TargetPage": "abbd0d46-a3d3-41ee-acb2-04fbd2ec535f"
                },
                {
                    "TargetPage": "START_PAGE"
                }
            ],
            "Triggered Transition Names": [
                "aedea5a9-9b3a-43c3-8206-c89685bf415c",
                "978d2fbb-5dca-4b55-9131-fd3e38c708b5"
            ]
        },
        "webhookStatuses": [
            {}
        ],
        "match": {
            "intent": {
                "name": "projects/hospitality-demo-361210/locations/global/agents/fcb0a3b6-8299-4a9d-87e0-3731db89eab2/intents/00000000-0000-0000-0000-000000000000",
                "displayName": "Default Welcome Intent"
            },
            "resolvedInput": "Hello",
            "matchType": "INTENT",
            "confidence": 1
        }
    },
    "responseType": "FINAL"
}
```


List conversations v2
https://global-dialogflow.googleapis.com/v2/projects/hospitality-demo-361210/locations/global/conversations/
