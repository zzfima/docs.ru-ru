---
title: "&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку &quot;&lt;имя_сборки&gt;&quot;. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30971"
  - "vbc30971"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30971"
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку &quot;&lt;имя_сборки&gt;&quot;.
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<сообщение\> Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<имя\_сборки\>". В этом случае попробуйте заменить ссылку на файл "\<имя\_файла\_сборки\>" в проекте "\<имя\_проекта1\>" на ссылку на проект "\<имя\_проекта2\>".  
  
 Код в проекте обращается к члену другого проекта, но конфигурация решения не позволяет компилятору [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] разрешить ссылку.  
  
 Для доступа к типу, определенному в другой сборке, компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.  
  
 **Идентификатор ошибки:** BC30971  
  
### Исправление ошибки  
  
1.  Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.  
  
2.  В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.  
  
## См. также  
 [Управление ссылками в проекте](/visual-studio/ide/managing-references-in-a-project)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылок"](http://msdn.microsoft.com/ru-ru/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB. Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Диагностика неработающих ссылок](/visual-studio/ide/troubleshooting-broken-references)