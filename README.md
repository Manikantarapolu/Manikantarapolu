# Manikanta Rapolu

SOC Analyst (L1) candidate in Hyderabad. B.Tech Cybersecurity graduate, 2026.

I started teaching myself security on 4 July 2026 with networking. I finished the TryHackMe SOC Level 1 path on 19 November and hold the Google Cybersecurity Professional Certificate. Everything below is work I did myself, and every verdict comes from evidence I collected.

## Sentinel lab

I built a Microsoft Sentinel lab in Azure with a Windows Server 2022 VM and wrote three KQL analytics rules: multiple failed logons (T1110), suspicious PowerShell (T1059.001), and a new local admin account (T1136.001 and T1098). I ran one attack chain against my own VM: six wrong passwords then a success, a PowerShell IEX command, a new admin account, and the Security log cleared twice. Each rule opened one incident, and I wrote four investigations with verdicts.

The rules had problems and I documented them. Overlapping lookback windows created duplicate alerts, and alert grouping merged them but the duplicates stay underneath. The admin rule first fired on every group add, including the automatic add to Users. The failed-logon rule does not catch the successful logon that follows. No rule covered a cleared Security log (event 1102) until I found it with a query.

Repo: [Sentinel-soc-lab](https://github.com/Manikantarapolu/Sentinel-soc-lab)

## Phishing investigations

I analyzed three emails from the Phishing Pot sample set by hand, with no scripts: a casino promo, a fake Ledger data-breach email asking for a recovery phrase, and a fake Microsoft terms update. In the Ledger email, SPF and DKIM passed for sendgrid.net but DMARC failed for recovery.com. The Microsoft email passed SPF, DKIM and DMARC, used a disguised sender name, and carried three .mobileconfig attachments. Each case has a report with evidence screenshots.

Repo: [phishing-email-investigation](https://github.com/Manikantarapolu/phishing-email-investigation)

## Notes

My notes for all 14 modules of the TryHackMe SOC Level 1 path are in [soc-analyst-notes](https://github.com/Manikantarapolu/soc-analyst-notes), one markdown file per module.

## Contact

I am looking for a SOC Analyst (L1) role in Hyderabad.

- LinkedIn: https://www.linkedin.com/in/manikanta-rapolu-8910a3354/
- Email: manikantarapolu97@gmail.com
