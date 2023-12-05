---
title: Macbook Setting
date: 2023-12-05 20:00:00 +09:00
categories: [Mac, Setting]
tags: [mac]     # TAG names should always be lowercase
toc: true
toc_sticky: true
---

# 언젠가 맥북을 다시 설정하는 날이 있을 때 한번에 해결하기 위한 포스트

## Karabiner
- 마우스를 사용할 시 인터넷 환경에서 뒤로가기 앞으로가기를 활성화 시키기
	- Karabiner를 설치 후 여러 권한들 허용
	- Karabiner-Elements &rarr; Complex Modifications &rarr; Add rule
	- 하단의 Import &rarr; Change mouse buttons (rev 2) Import
	- Change button4,5 to back,forward (rev 1) Enable
	- Devices &rarr; Mouse의 Modifiy events 활성화

## Homebrew
- 터미널에서 homebrew 설치하기
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- 버전 확인
```
brew --version
```

- 오류 발생시
```
	$ brew --version
	zsh: command not found: brew

	# zshrc에 homebrew path 추가
	$ echo 'export PATH=/opt/homebrew/bin:$PATH' >> ~/.zshrc
	# zshrc 반영
	$ source ~/.zshrc
```

## Iterm2
```
brew install --cask iterm2
```
- Appearance &rarr; Theme - Minimal
- Profiles &rarr; Session &rarr; Status bar enabled (세부설정으로 여러가지 설정가능)
- Profiles &rarr; Colors &rarr; Color Presets로 다운 받은 iterm2 color 적용
- iCloud 접근
	- /Users/UserName/Library/Mobile\ Documents/com~apple~CloudDocs

## Oh-my-zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
- p10k
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
- 테마 적용
	- vi ~/.zshrc &rarr; ZSH_THEME="ZSH_THEME="powerlevel10k/powerlevel10k"
	- 재실행
	- Meslo Nerd Font 설치 후 재실행
	- 아이콘이 다 보이면 y
	- 세부 테마 설정
	- 3 &rarr; 1 &rarr; 1 &rarr; 3 &rarr; 1 &rarr; 1 &rarr; 1 &rarr; 1 &rarr; 2 &rarr; 1 &rarr; n &rarr; 1 &rarr; y 
- 추천 플러그인

bat
```
brew install bat
```
fd
```
brew install fd
```
auto suggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
syntax highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

$vi ~/.zshrc
source ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```
autojump
```
brew install autojump
```

## gh
```
brew install gh
```

## VSCode
- homebrew를 통해 vscode 설치하기
```
brew install --cask visual-studio-code
```
- --cask는 GUI 응용프로그램 설치할 때 (~/Applications에 설치됨)
- 깔면 좋은 익스텐션
	- Korean Language Pack for Visual Studio Code (대부분 기본 설치)
	- Git Graph
	- Jupyter / Jupyter PowerToys
	- Material Icon Theme
	- Prettier
- terminal font family
	- MesloLGS NF

## anaconda3
- homebrew를 통해 anaconda 설치하기
```
brew install --cask anaconda
```
- 버전 확인
```
conda -V
```
- 오류 발생시
```
$ echo 'export PATH=/opt/homebrew/anaconda3/bin:$PATH' >> ~/.zshrc
$ source ~/.zshrc
```

## Ruby & Jekyll
- github blog 로컬 테스트를 위한 jekyll 설치
```
	brew install rbenv ruby-build

	rbenv install -l

	rbenv install 3.2.2 (2023-12-06 기준)

	$ vi ~/.zshrc

	[[ -d ~/.rbenv  ]] && \
  	export PATH=${HOME}/.rbenv/bin:${PATH} && \
  	eval "$(rbenv init -)"

	rbenv global 3.2.2

	bundle install

	gem install jekyll bundler
```
