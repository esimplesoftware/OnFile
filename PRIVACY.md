# Onfile Privacy Statement

Last updated: October 9, 2026

This statement explains what information the Onfile desktop software (the "Software") and Carlton Ray, doing business as eSimpleSoftware ("we", "us"), collect, and what stays on your computer.

## Summary

- Onfile indexes file names on your computer. The index stays on your computer and is encrypted.
- Onfile never sends file names, folder paths, search text, or your computer name to us or anyone else.
- The only network traffic is license activation and checks, handled by our payment and licensing provider, Polar.

## Information that stays on your computer

| Item | Where | Protection |
|------|-------|------------|
| File index (`onfile.db`) | `%APPDATA%\Onfile` or a folder you choose | Encrypted with a random key sealed to your Windows account |
| License record (`license.dat`) | Same folder | Sealed to your Windows account |
| Settings (`onfile.ini`) | Same folder | Plain text. Lists the drives and shares you added, filters, and schedules. No searches |
| Log (`onfile.log`) | Same folder | Plain text. Drives, record counts, and errors. No file names or searches |
| Verbose log (`onfile.log.verbose`) | Same folder | Only when started with `--verbose`. File names and searches are hidden unless you also add `--verbose-names`. Deleted on the next normal start |
| Helper log (`usn-helper.log`) | `%LOCALAPPDATA%\Onfile` | Plain text. Drive letters, service status, and errors. No file names |

We cannot see any of this. It is only shared if you choose to send it to us, for example a log file with a support request.

Onfile does not keep search history, does not export results, and does not send crash reports.

## Information sent over the internet

Onfile contacts Polar's license service (`api.polar.sh`) only in these cases:

| When | What is sent |
|------|--------------|
| Activation | License key, a random device ID (for example `Onfile PC 7F3A`) |
| Each start (license check) | License key, activation ID |
| Deactivation | License key, activation ID |

As with any internet connection, Polar receives your IP address. The random device ID is shown in Onfile's License dialog so you can tell your PCs apart when managing activations. It is not derived from your computer name or hardware.

## Purchases

Polar Software, Inc. is the merchant of record for Onfile. When you buy a license, Polar collects your name, email address, billing details, and payment information, and processes them under its own privacy policy:

https://polar.sh/legal/privacy-policy

We receive your name, email address, and order details from Polar so we can provide your license and support. We do not receive your full card number.

## How we use information

We use purchase and license information only to:
- issue, activate, and verify licenses,
- respond to support requests,
- meet legal and tax obligations.

We do not sell personal information and do not use it for advertising.

## Clipboard

**Copy path** and **Copy name** put text on the Windows clipboard. If Windows clipboard history or cloud clipboard is turned on, Windows may keep that text. This is controlled by Windows, not Onfile.

## Your choices

- Uninstall Onfile and delete `%APPDATA%\Onfile` and `%LOCALAPPDATA%\Onfile` to remove all local data.
- Deactivate a license from the License dialog or the Polar customer portal.
- To ask about, correct, or delete the purchase information we hold, contact us below. For information held by Polar, see Polar's privacy policy.

## Children

Onfile is not directed to children under 13, and we do not knowingly collect their information.

## Changes

We will update this statement if Onfile's data handling changes, and change the date above.

## Contact

Carlton Ray, eSimpleSoftware
Jackson, Tennessee 38305
Email: esimplesoftware@gmail.com
