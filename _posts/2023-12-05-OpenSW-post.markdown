---
layout: post
title:  "마지막 작업"
description: 안녕 openSW
date:   2023-12-05 9:05:10 +9
categories: Pygame OpenSW
---

### <span style = 'background-color:#fff5b1'>마지막 게임 제작기 포스팅</span>

마지막 수업에 앞서 우리조는 게임 UI 관련 회의를 통해 최종 수정 사항을 결정했다. 
<br><br>

### 최종 UI 디자인 회의 진행 결과 
* MouseHover 발생 시 사용자가 어떤 게임을 선택했는지 보여주자!
* UI 디자인을 수정하자!
* Q를 눌렀을 때 플레이 하던 중 창 닫고 메인 화면으로 돌아오는 기능 추가하자!
* readme.md 파일 수정

위와 같은 사항을 이슈로 지정했고, 조원 별로 하나씩 맡아서 작업했다.

내가 맡은 것은 **UI 디자인**과 **Q 눌렀을 때 게임 창 닫기** 기능 구현이었다. 
<br><br>

### <span style = 'background-color:#fff5b1'>UI 디자인</span>
![designUI](/image/post_231205/uiDesign.png)
우리조의 게임명은 '삼선 짬뽕'이다. 
이에 따라 RED와 짬뽕 일러스트를 사용한 심플한 디자인의 간단 디자인 기획서를 작성하고 이를 토대로 작업을 시작했다. 

![imageCode](/image/post_231205/codeBackGround.png)
기존 코드에서 배경 이미지를 다루는 코드를 수정하여 아래와 같이 배경에 깔아줬다.

```python
menu_font = pygame.font.Font(None, 50)
help_font = pygame.font.Font(None, 60)
clock = pygame.time.Clock()

for i, game_name in enumerate(game_names):
    text = menu_font.render(game_name, True, (0, 0, 0))
    text_rect = text.get_rect(center=(width//1.3, 250 + i * 60))

    if text_rect.collidepoint(pygame.mouse.get_pos()):
        text = menu_font.render(game_name, True, (255, 255, 255))
        selected_game = game_names[i]

    screen.blit(text, text_rect)


display_text(screen, help_font, f"Press 'Q' button to stop play!", width // 2, height // 5.5, (255, 0, 0))
display_text(screen, help_font, f"Selected Game: {selected_game}", width // 2, height - 50, (0, 0, 0))

```

이후, 배열을 활용해서 게임명을 보여주는 코드의 수치값을 수정하여 우측으로 위치를 옮겨준다. 

상단, 우측 폰트의 사이즈를 각각 조절하기 위해 변수를 따로 설정해주면 text 버튼의 위치 조정까지 완료!

한 가지 헤맸던 것은 버튼의 위치는 원하는 곳으로 옮겼는데, **버튼 눌렀을 때 게임 창이 열리지 않는 문제가 발생**했다.  

```python
text_rect = menu_font.render(game_names[i], True, (0, 0, 0)).get_rect(center=(width//1.3, 250 + i * 60))
                    
```
이는 text와 서브창을 띄우는 기능을 따로 구현했기 때문이었다.
즉, 버튼을 눌렀을 때 새창이 열리는 것이 아닌, 해당 위치를 마우스로 클릭했을 때 새창이 뜬다는 것.

따라서, 클릭하는 위치를 옮긴 text의 위치로 변경해주었더니 새 창이 잘 뜬다 

hover 기능도 팀원분이 구현해주셔서 마우스가 hover 되었을 때 text가 흰색으로 변한다.

### ⏬ 최종 완성된 UI이다! 
![mainUI](/image/post_231205/mainUI.png)

### ### <span style = 'background-color:#fff5b1'>Q 눌렀을 때 각 게임창이 닫히도록 구현 </span>

```python
elif event.type == KEYDOWN:
    if event.key == K_q:
        pygame.quit()
        sys.exit()
```
플레이를 하는 도중 창을 닫고 메인 메뉴로 돌아가 다른 게임을 선택할 수 있는 기능 구현이 필요했다. 

따라서, 기존에 main에서 구현해둔 코드 중 Q 버튼을 눌렀을 때 메인 메뉴 창이 닫히도록 구현해둔 코드를 각 게임 파일에 넣어주었다. 

각 팀원별로 게임 동작 방식이 달랐다.
게임을 종료하는 코드는 세 게임 모두 구현이 되어있었기에 코드를 살펴보고 종료하는 코드를 event loop 안에 Q 버튼 press 조건문을 넣고, 안에 넣어주는 방식으로 진행했다. 

1. **기억력 게임**
```python
elif event.type == KEYDOWN:
    if event.key == K_q:
        running = False
```
기억력 게임의 경우 running이라는 변수가 있어서 해당 변수값을 false로 설정했을 때 게임이 종료되는 방식이었다. 

2. **피하기 게임**
```python
elif event.type == pygame.KEYDOWN:
    if event.key == pygame.K_q:
        running = False
```
피하기 게임의 경우 running을 false로 설정해주는 것은 기억력 게임과 동일했으나, event를 불러오는 방식이 pygame을 추가적으로 붙여줘야 했음.

3. **지렁이 게임**
```python
 elif event.type == pygame.KEYDOWN:
    if event.key == pygame.K_q:
        quit()
```
지렁이 게임의 경우 event 불러오는 방식은 피하기 게임과 동일했으나, quit() 메서드를 활용해 게임을 종료하는 방식이었다. 


끝!