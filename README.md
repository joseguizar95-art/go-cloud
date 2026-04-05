# The Go Cloud Development Kit (Go CDK)

_Write once, run on any cloud ☁️_

[![Build Status](https://github.com/google/go-cloud/actions/workflows/tests.yml/badge.svg?branch=master)](https://github.com/google/go-cloud/actions)
[![Go Report Card](https://goreportcard.com/badge/github.com/google/go-cloud)](https://goreportcard.com/report/github.com/google/go-cloud)
[![PkgGoDev](https://pkg.go.dev/badge/mod/gocloud.dev)][PkgGoDev]
[![Coverage](https://codecov.io/gh/google/go-cloud/branch/master/graph/badge.svg)](https://codecov.io/gh/google/go-cloud)
![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/google/go-cloud)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

<p align="center">
  <img width="509" height="276" src="internal/website/static/go-cdk-logo-gopherblue.png" alt="">
</p>

The Go Cloud Development Kit (Go CDK) allows Go application developers to
seamlessly deploy cloud applications on any combination of cloud providers. It
does this by providing stable, idiomatic interfaces for common uses like storage
and databases. Think `database/sql` for cloud products.

Imagine writing this to read from blob storage (like Google Cloud Storage or
S3):

```go
ctx := context.Background()
bucket, err := blob.OpenBucket(ctx, "s3://my-bucket")
if err != nil {
    return err
}
defer bucket.Close()
blobReader, err := bucket.NewReader(ctx, "my-blob", nil)
if err != nil {
    return err
}
```

and being able to run that code on any cloud you want, avoiding all the ceremony
of cloud-specific authorization, tracing, SDKs and all the other code required
to make an application portable across cloud platforms.

The project works well with a code generator called
[Wire](https://github.com/google/wire/blob/master/README.md). It creates
human-readable code that only imports the cloud SDKs for services you use. This
allows the Go CDK to grow to support any number of cloud services, without
increasing compile times or binary sizes, and avoiding any side effects from
`init()` functions.

You can learn more about the project from our [announcement blog post][], or our
talk at Next 2018:

[![Video: Building Go Applications for the Open Cloud (Cloud Next '18)](https://img.youtube.com/vi/_2ZwhvIkgek/0.jpg)][video]

[announcement blog post]: https://blog.golang.org/go-cloud
[PkgGoDev]: https://pkg.go.dev/mod/gocloud.dev
[travis]: https://travis-ci.com/google/go-cloud
[video]: https://www.youtube.com/watch?v=_2ZwhvIkgek

## Installation

```shell
# First "cd" into your project directory if you have one to ensure "go get" uses
# Go modules (or not) appropriately. See "go help modules" for more info.
go get gocloud.dev
```

The Go CDK builds at the latest stable release of Go. Previous Go versions may
compile but are not supported.

## Documentation

Documentation for the project lives primarily on https://gocloud.dev/, including
[tutorials][].

You can also browse Go package reference on [pkg.go.dev][PkgGoDev].

[tutorials]: https://gocloud.dev/tutorials/

## Project status

The APIs are still in alpha, but we think they are production-ready and are
actively looking for feedback from early adopters. If you have comments or
questions please open an issue.

At this time we prefer to focus on maintaining the existing APIs and drivers,
and are unlikely to accept new ones into the `go-cloud` repository. The modular
nature of the Go CDK makes it simple to host new APIs and drivers for existing
APIs externally, in separate repositories.

If you have a new API or driver that you believe are important and mature enough
to be included, feel free to open an issue to discuss this; our default will
likely be to suggest starting in a separate repository. We'll also be happy
to maintain a list of such external APIs and drivers in this README.

## Current features

The Go CDK provides generic APIs for:

*   Unstructured binary (blob) storage
*   Publish/Subscribe (pubsub)
*   Variables that change at runtime (runtimevar)
*   Connecting to MySQL (including MariaDB) and PostgreSQL databases (mysql, postgres)
*   Server startup and diagnostics: request logging, tracing, and health
    checking (server)

## Contributing

Thank you for your interest in contributing to the Go Cloud Development
Kit! :heart:

Everyone is welcome to contribute, whether it's in the form of code,
documentation, bug reports, feature requests, or anything else. We encourage you
to experiment with the Go CDK and make contributions to help evolve it to meet
your needs!

The GitHub repository at [google/go-cloud][go-cloud] contains some driver
implementations for each portable API. We intend to include
[Google Cloud Platform][gcp], [Amazon Web Services][aws], and [Azure][azure]
implementations, as well as prominent open source services and at least one
implementation suitable for use in local testing. Unfortunately, we cannot
support every service directly from the project; however, we encourage
contributions in separate repositories.

If you create a repository that implements the Go CDK interfaces for other
services, let us know! We would be happy to link to it here and give you a
heads-up before making any breaking changes.

See [the contributing guide](./CONTRIBUTING.md) for more details.

[go-cloud]: https://github.com/google/go-cloud
[gcp]: http://cloud.google.com
[aws]: http://aws.amazon.com
[azure]: https://azure.microsoft.com/

## Community

This project is covered by the Go [Code of Conduct][].

[Code of Conduct]: ./CODE_OF_CONDUCT.md

## Legal disclaimer

The Go CDK is open-source and released under an [Apache 2.0
License](https://github.com/google/go-cloud/blob/master/LICENSE). Copyright ©
2018–2019 The Go Cloud Development Kit Authors.

If you are looking for the website of GoCloud Systems, which is unrelated to the
Go CDK, visit https://gocloud.systems.
Installing an OAuth app in your organization

You can install OAuth apps from GitHub Marketplace to use in your organization.

About installing OAuth apps in your organization

> [!NOTE]
> This article applies to installing and purchasing apps from GitHub Marketplace only. For more information on apps purchased from integrators, see About GitHub integrations.

> [!TIP]
> If an app requires organization-level access, then only an organization owner can purchase, install, or cancel the app, and manage app billing for the organization. If the app doesn't require organization-level access, then a repository administrator can install and uninstall the app.

If you choose a paid plan, you'll pay for your app subscription on your organization's current billing date using your organization's existing payment method.

If you choose a paid plan with a free trial, you can cancel at any time during your trial period without being charged, but you will automatically lose access to the app. Your paid subscription will start at the end of the 14-day trial. For more information, see GitHub Marketplace app subscriptions.

For more information about installing a GitHub App, see Installing a GitHub App from GitHub Marketplace for your organizations.

Installing an OAuth app in your organization

If you belong to any organizations that enforce SAML single sign-on, you may be prompted to authenticate through your identity provider before you can authorize an OAuth app. For more information about SAML, see About authentication with single sign-on.

To open GitHub Marketplace, in the top-left corner of GitHub, select <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-three-bars" aria-label="Open global navigation menu" role="img"><path d="M1 2.75A.75.75 0 0 1 1.75 2h12.5a.75.75 0 0 1 0 1.5H1.75A.75.75 0 0 1 1 2.75Zm0 5A.75.75 0 0 1 1.75 7h12.5a.75.75 0 0 1 0 1.5H1.75A.75.75 0 0 1 1 7.75ZM1.75 12h12.5a.75.75 0 0 1 0 1.5H1.75a.75.75 0 0 1 0-1.5Z"></path></svg>, then click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gift" aria-label="gift" role="img"><path d="M2 2.75A2.75 2.75 0 0 1 4.75 0c.983 0 1.873.42 2.57 1.232.268.318.497.668.68 1.042.183-.375.411-.725.68-1.044C9.376.42 10.266 0 11.25 0a2.75 2.75 0 0 1 2.45 4h.55c.966 0 1.75.784 1.75 1.75v2c0 .698-.409 1.301-1 1.582v4.918A1.75 1.75 0 0 1 13.25 16H2.75A1.75 1.75 0 0 1 1 14.25V9.332C.409 9.05 0 8.448 0 7.75v-2C0 4.784.784 4 1.75 4h.55c-.192-.375-.3-.8-.3-1.25ZM7.25 9.5H2.5v4.75c0 .138.112.25.25.25h4.5Zm1.5 0v5h4.5a.25.25 0 0 0 .25-.25V9.5Zm0-4V8h5.5a.25.25 0 0 0 .25-.25v-2a.25.25 0 0 0-.25-.25Zm-7 0a.25.25 0 0 0-.25.25v2c0 .138.112.25.25.25h5.5V5.5h-5.5Zm3-4a1.25 1.25 0 0 0 0 2.5h2.309c-.233-.818-.542-1.401-.878-1.793-.43-.502-.915-.707-1.431-.707ZM8.941 4h2.309a1.25 1.25 0 0 0 0-2.5c-.516 0-1 .205-1.43.707-.337.392-.646.975-.879 1.793Z"></path></svg> Marketplace.

   ￼

Browse to the app you'd like to install, then click on the app's name.
On the app's page, under "Pricing and setup," click the pricing plan you'd like to use.
Click Install it for free, Buy with GitHub, or Try free for 14 days.
Choose an installation organization for the app. Depending on your organization's terms of service, this process will be slightly different.
If you have given GitHub permission to collect name and address information for your organization, in the "Billing information" section, select the Switch billing account <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-triangle-down" aria-label="The downwards-facing triangle icon" role="img"><path d="m4.427 7.427 3.396 3.396a.25.25 0 0 0 .354 0l3.396-3.396A.25.25 0 0 0 11.396 7H4.604a.25.25 0 0 0-.177.427Z"></path></svg> dropdown menu, then click the organization in which you'd like to install the app.

   ￼

Otherwise, under "Review your order," select the Account dropdown menu, then click the organization in which you'd like to install the app.

   ￼

If you chose a paid plan, review your payment method.
To change the existing payment method on file for the organization, click Edit, then complete the form to add a new payment method.
If there isn't a payment method on file for the organization, click Add a Payment Method, then complete the form to add a credit card or PayPal account.
Click Complete order and begin installation.
Review the information about the app's access to your personal account, organizations, and data, then click Authorize application.

Further reading

Managing your payment and billing information
Installing an OAuth app in your personal account

