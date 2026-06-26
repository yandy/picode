# Pi Config for Coding

## 1. Setup

```sh
# install pi
npm install -g @earendil-works/pi-coding-agent

# clone config
git clone https://github.com/yandy/picode.git ~/.pi/agent-code
cp ~/.pi/agent-code/models.json{.tmpl,}
```

### add `picode`

**fish**

`~/.config/fish/conf.d/pi.fish`

```fish
function picode
  env PI_CODING_AGENT_DIR=$HOME/.pi/agent-code pi $argv
end
```

**bash**

`~/.bashrc`

```fish
picode() {
  PI_CODING_AGENT_DIR="$HOME/.pi/agent-code" pi "$@"
}
```

## 2. Skills Management

### 2.1 Add skill

```sh
npx skills add <package> --skill <skills> -a pi -y
# eg.
npx skills add anthropics/skills --skill pdf docx -a pi -y
```

### 2.2 Update skills

```sh
npx skills update -a pi
```

### 2.3 Remove skills

```sh
npx skills remove <skills> -a pi
```

### 2.4 List skills

```sh
npx skills ls -a pi
```

### 2.5 Current skills

- skill-creator

```sh
# npx skills add anthropics/skills --skill skill-creator -a pi -y
```

- office

```sh
# npx skills add anthropics/skills --skill pdf -a pi -y
```

- ui/ux

```sh
# npx skills add nextlevelbuilder/ui-ux-pro-max-skill --skill ui-ux-pro-max -a pi -y
# npx skills add alchaincyf/huashu-design --skill huashu-design -a pi -y
```

- browser automation

```sh
npm install -g playwright @playwright/cli
playwright install chromium firefox
# npx skills add microsoft/playwright-cli --skill playwright-cli -a pi -y
```

- [context7](https://github.com/upstash/context7)

```sh
npx ctx7 login
# npx ctx7 setup --pi
```
