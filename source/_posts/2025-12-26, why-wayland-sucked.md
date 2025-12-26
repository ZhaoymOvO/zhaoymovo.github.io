---
title: Why Wayland sucked?
date: 2025-12-26 16:09:54
categories:
  - Computer 
tags:
  - Linux
  - GUI
  - Desktop
---
我曾經多次在公開場合拒絕使用Wayland
and that's why: ***Y***

---

好了，是時候認證講講爲什麼了

很多人講啊你現在是不是要開始給那個不知道多少年沒更新的X11辯護了
恭喜你答對了
我們來講講爲什麼我認爲Wayland的開發理念必然做不好圖形化界面

很多Linux Desktop用戶都沒有搞明白的一點是，desktop client os面向的對象根本不在意什麼開源什麼模塊化
大家需要的只有oob之後可以直接ready to go，需要的是一架買來可以直接用的車，而不是可以拆卸替換每一個組件的車
這點和do one thing and do it well的UNIX哲學是衝突的，或者說，你得有人想辦法給這一切串起來

Wayland遵循的就是do one thing and do it well的UNIX哲學
我只負責給畫面送上屏幕，其他的compositor也好shell也罷自己解決問題吧
最後的結果是怎樣？結果是同樣的軟件在GNOME下在Plasma下，甚至同樣的desktop environment但是不同的compositor配置下的表現都完全不同
相信我，體驗的不統一是Linux desktop不能普及的最大阻礙

而反觀我們的good old X11呢？
X11針對你能想到的大部分工作都提供了接口，輸入處理、窗口合成、熒幕管理，通通都是X11在處理
對於X11而言，再怎麼差異化的硬件下軟體的表現也是類似的，大家只要對接好X11的接口就OK了

Desktop experience本就是高度整合的場景，用戶需要的不是每一個零件可以自由的組裝，用戶需要的是整體用起來沒有割裂感
Wayland的do one thing and do it well的設計理念，增加了桌面體驗的整合成本，最終轉嫁到下游開發者（desktop environmen, compositor, shell, display manager, ...）、發行版和用戶頭上

是，現在的大家已經在爲了Wayland的體驗在整合下游的protocol了
但是對於一個大家滿腦子都是自己代碼寫爽，出一個整合度比較高的systemd都能被炎上的社區，這種融合很顯然是道阻且長的（且不知道會不會被Wayland自己背刺）

_X.org沒有未來，而Wayland只有未來_
