---
uid: General_Main_Release_10.4.0_new_features
---

# General Main Release 10.4.0 – Other new features - Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

### DMS web apps

#### Dashboards app & low-code apps: Icon component [ID_34867]

<!-- MR 10.4.0 - FR 10.3.1 -->

The new icon component allows you to display an icon on a dashboard or a low-code app.

#### Interactive Automation scripts: New button style 'CallToAction' [ID_34904]

<!-- MR 10.4.0 - FR 10.3.1 -->

In an interactive Automation script launched from a dashboard or a low-code app, you can now apply the *CallToAction* style to a button.

When you apply this style to a button

- the background color of the button will be the color of the app,
- the color of the text on the button will be white, and
- the button will have a shadow.

To set the style of a button in an interactive Automation script, set the *Style* property of the button's *UIBlockDefinition* to the name of the style. All supported styles are available via `Style.Button`.

Alternatively, you can also pass a button style directly to the `AppendButton` method on an `UIBuilder` object.

> [!NOTE]
>
> - Up to now, `StaticText` blocks already supported a number of styles. Those styles are now also available via `Style.Text`: *Title1*, *Title2* and *Title3*.
> - The *CallToAction* style will only be applied in interactive Automation scripts launched from a web app. It will not be applied in interactive Automation scripts launched from Cube.

### DMS Tools

#### SLNetClientTest tool - 'Connect' window: Enhanced 'Connection Type' and 'Authentication' sections [ID_34712]

<!-- MR 10.4.0 - FR 10.3.1 -->

In the *SLNetClientTest* tool, to connect to a DataMiner Agent, you select *Connection* > *Connect*, and specify the necessary information in the *Connect* window. That window has now been updated.

In the *Connection Type* section, you now have to indicate how the connection has to be established:

| Select...              | in order to... |
|------------------------|----------------|
| Autodetect             | connect to the local machine or a remote machine using the method that will be detected automatically. |
| gRPC                   | connect to the local machine or a remote machine via the APIGateway service using the GRPCWeb protocol.<br>When you choose this option, you can specify a custom port (default: `443`) and a custom endpoint (default: `/APIGateway`). |
| .NET Remoting (legacy) | connect to the local machine or a remote machine using .NET Remoting.<br>When you choose this option, you can specify a custom port (default: `8004`) |
| IPC (only local)       | connect to the local machine using IPC. |

In the *Authentication* section (formerly known as *User Info* section), you now have the following authentication options:

- Single sign-on

    > [!NOTE]
    > External authentication not yet supported.

- Explicit credentials (with *Force Authenticate Local User* option)

- Ticket

> [!WARNING]
> Always be extremely careful when using this tool, as it can have far-reaching consequences on the functionality of your DataMiner System.
