# drachtio-dialogflow-phone-gateway-tadhack

An open source telephony gateway for Google's [dialogflow](dialogflow.com) using [Simwood](https://simwood.com/) IP trunks.

The following environment variables are used to provide run-time configuration to the application (optionally, a configuration file can be used instead of environment variables; see config/local.json.example for details).

#### Application configuration

|Environment Variable Name|Description| Required?|
|------------|---------|---------|
|GOOGLE_APPLICATION_CREDENTIALS|path to a json key file containing GCP credentials used to authenticate to dialogflow|Yes|
|DIALOGFLOW_PROJECT|the dialogflow project id to connect calls to|Yes|
|DIALOGFLOW_LANG|language to use for the dialogflow session|No (default: en-us)|
|DIALOGFLOW_WELCOME_EVENT|name of initial event to send to dialogflow when connecting call|No|
|DIALOGFLOW_NO_INPUT_TIMEOUT|number of seconds of no detected intent to allow to pass before reprompting the caller|No|
DIALOGFLOW_ENABLE_DTMF_ALWAYS| if 1, dtmf will always be collected and sent to dialogflow as a text input|No(default: 1)|
|DIALOGFLOW_INTERDIGIT_TIMEOUT|number of milliseconds to wait after collecting a dtmf before sending the collected dtmf digits to dialogflow as a text query|No (default: 3000)|
|DIALOGFLOW_BARGE_PHRASE|a phrase that when uttered by the caller will cause audio playback to the caller to cease|No|
|DIALOGFLOW_THINKING_SOUND|path to an audio file (wav or mp3) to play while dialogflow intent detection and back-end fulfillment are proceeding|No|
|HTTP_PORT|http port of websocket server to listen on for incoming client connections|No|
|SIP_TRUNK_GATEWAY|IP address or DNS to send outbound INVITEs to for call transfer|No, but call transfer will be disabled if not specified|
|SIP_OUTDIAL_CLI|CLI to use on outdials|Yes, if call transfer is enabled|
