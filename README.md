# Detection as Code

A public repository of security detection rules where every rule is proven by a real simulated attack.

For each technique in the MITRE ATT&CK framework, this project keeps four things together: a recorded attack, a detection rule, an automatic test, and a line on the coverage table below. If a rule stops matching its recorded attack, the build fails. We add one new technique every week.

Built by Abdulmujeeb Uthman and Rita.

## How it works

1. **Attack:** we run a safe simulation of one technique on our own lab machine and record the logs.
2. **Rule:** we write a detection rule (Sigma, and a Wazuh version) mapped to the technique ID.
3. **Test:** on every pull request, GitHub Actions replays the recorded logs through the rule and checks that the expected alert fires.
4. **Coverage:** the table below shows what we can detect today.

## Coverage

| ATT&CK ID | Technique         | Attack recorded | Rule    | Test    |
| --------- | ----------------- | --------------- | ------- | ------- |
| T1110     | Brute Force (SSH) | Pending         | Pending | Pending |

Status values: Pending, In progress, Done.

## Repository layout

```
attacks/             one note per technique, with the exact attack steps
logs/                recorded sample logs, one folder per technique
rules/sigma/         Sigma rules, named by technique ID
tests/               replay tests and the alerts each log must produce
docs/                coverage page and technique write ups
.github/workflows/   automated checks on every pull request
```

## Ground rules

- Attacks run only on machines we own, inside our own lab.
- Logs are cleaned before they are committed. No real IP addresses, usernames, passwords, keys, or tokens.
- No client, employer, or internship material.
- Every change goes through a pull request with one review.

## Contributing

Open an issue to suggest a technique, or send a pull request that includes the attack note, the recorded log, the rule, and the expected alert.

## Licence

MIT. See the LICENSE file.
