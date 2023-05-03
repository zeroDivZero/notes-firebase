# PROJECT

<https://console.firebase.google.com/>

![Project](/assets/project.png)

Logical container of apps, accessible from console. Place to configure services and products for variants of app. Apps in same container share resources like **Realtime Database** and **Analytics**.

## Users and Permissions

To set up users and access control.
![Users and Permissions](/assets/users-permissions.png)

## Billing

Can check usage and billing, switch plan, etc.

## App Organization

Apps that have same business use case -- represent same app on different platforms -- should be in same Project. Can create apps for Android, iOS, Web, Unity, and Flutter.

Besides sharing resources, integrations with other tools also shared. Once Slack integration done, applicable to all apps registered in same Project.

## Best Practices

If all app variants in same Project, user can move from one platform to another using same login.

Two apps on same platform, say free and paid, should also be in same Project.

Since analytics are shared, if need team member only see analytics for one platform and not others, apps should be in separate Projects, but loses shared resources. If need users to sign in to all platforms, need to implement custom authentication (minting own tokens and exchanging with Firebase).

When private or white labeling (same app basis but branded differently), should be in separate Projects.

Rule of thumb: One Project per logo.

## Cost

Free plan, **Spark Plan**, allows access to most features. When exceeding limits, apps shut off until next month. With paid plan, **Blaze Plan**, only pay for actual usage.
