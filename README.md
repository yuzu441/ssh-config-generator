# honeydew

## how to use

install:

```sh
npm i -g @yuzu441/honeydew
```

To run:

Create ssh config file. The file name must end with `.config.ts`.

```typescript
// config/example.com.config.ts
import { SshConfig } from "@yuzu441/honeydew"

export default new SshConfig("example.com", {
  hostname: "example.com",
  port: 22,
  user: "yuzu",
  identityFile: "~/.ssh/key1",
})
```

```bash
honeydew --config=./config/ --output=~/.ssh/config
```

generated config. If the `--output` flag is omitted, the output will be sent to stdout.

```
#
# This config is generated by ssh-config-generator v0.0.1
# 2024-04-01 22:13:33
#

Host example.com
  HostName example.com
  Port 22
  User yuzu
  IdentityFile ~/.ssh/key1
```