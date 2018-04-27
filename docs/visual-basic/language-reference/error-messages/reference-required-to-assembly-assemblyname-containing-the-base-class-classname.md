---
title: Требуется ссылка на сборку &#39; &lt;assemblyname&gt; &#39; содержит базовый класс &#39; &lt;classname&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6dd53e2d0bf0535de50e465293edb26a5b1d484
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Требуется ссылка на сборку &#39; &lt;assemblyname&gt; &#39; содержит базовый класс &#39; &lt;classname&gt;&#39;
Требуется ссылка на сборку "\<имя_сборки >" содержит базовый класс\<имя_класса > ". Добавьте эту ссылку в проект.  
  
 Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки. Компилятор Visual Basic требует ссылку, чтобы избежать неоднозначности, если класс определен в нескольких DLL или сборках.  
  
 **Идентификатор ошибки:** BC30007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.  
  
## <a name="see-also"></a>См. также  
   
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)  
 [Диагностика неработающих ссылок](/visualstudio/ide/troubleshooting-broken-references)
