---
title: "Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID430"
dev_langs: 
  - "VB"
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Либо класс, указанный вами в вызове функции `GetObject` или `CreateObject`, не предоставил интерфейс программирования, либо вы изменили проект с .DLL на .EXE или наоборот.  
  
### Исправление ошибки  
  
1.  Просмотрите документацию по приложению, которое создало данный объект, чтобы узнать об ограничениях на использование автоматизации с объектом такого класса.  
  
2.  Если вы изменили проект с .DLL на .EXE или наоборот, необходимо вручную отменить регистрацию старого проекта .DLL или .EXE.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Обращайтесь к нам](/visual-studio/ide/talk-to-us)