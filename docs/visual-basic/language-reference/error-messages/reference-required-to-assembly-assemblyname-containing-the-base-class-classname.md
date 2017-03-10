---
title: "Требуется ссылка на сборку &quot;&lt;имя_сборки&gt;&quot;, содержащую базовый класс &quot;&lt;имя_класса&gt;&quot;. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30007"
  - "vbc30007"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30007"
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Требуется ссылка на сборку &quot;&lt;имя_сборки&gt;&quot;, содержащую базовый класс &quot;&lt;имя_класса&gt;&quot;.
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Требуется ссылка на сборку "\<имя\_сборки\>", содержащую базовый класс "\<имя\_класса\>". Добавьте эту ссылку в проект.  
  
 Класс определяется в библиотеке динамической компоновки \(DLL\) или в сборке, на которую в проекте нет прямой ссылки. Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] требует ссылки в целях устранения неоднозначности, если класс определен в нескольких библиотеках DLL или сборках.  
  
 **Идентификатор ошибки:** BC30007  
  
### Исправление ошибки  
  
-   Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.  
  
## См. также  
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылок"](http://msdn.microsoft.com/ru-ru/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Управление ссылками в проекте](/visual-studio/ide/managing-references-in-a-project)   
 [Диагностика неработающих ссылок](/visual-studio/ide/troubleshooting-broken-references)