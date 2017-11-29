---
title: "Требуется ссылка на сборку &#39; &lt;assemblyname&gt;&#39; содержащий базовый класс &#39;&lt; className&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords: BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7413c82a9c61d13e7ca6fa18f27a4769a0937f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Требуется ссылка на сборку &#39; &lt;assemblyname&gt;&#39; содержащий базовый класс &#39;&lt; className&gt;&#39;
Требуется ссылка на сборку "\<имя_сборки >" содержит базовый класс\<имя_класса > ". Добавьте эту ссылку в проект.  
  
 Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки. Компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] требует ссылки в целях устранения неоднозначности, если класс определен в нескольких библиотеках DLL или сборках.  
  
 **Идентификатор ошибки:** BC30007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.  
  
## <a name="see-also"></a>См. также  
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылок"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)  
 [Диагностика неработающих ссылок](/visualstudio/ide/troubleshooting-broken-references)
