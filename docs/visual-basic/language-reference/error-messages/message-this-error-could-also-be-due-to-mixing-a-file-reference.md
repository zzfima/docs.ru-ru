---
title: "&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку &quot;&lt;assemblyname&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
dev_langs:
- VB
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a1806fd078fc05d966c718841e5b78c1323a43c2
ms.lasthandoff: 03/13/2017

---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;сообщение&gt; Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "&lt;assemblyname&gt;"
\<сообщение настроек Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<assemblyname настроек. В этом случае попробуйте заменить ссылку на файл "\<assemblyfilename настроек" в проекте "\<projectname1 настроек" со ссылкой на проект "\<projectname2 настроек".  
  
 Код в проекте обращается к члену другого проекта, но конфигурация решения не позволяет [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятора для разрешения ссылки.  
  
 Для доступа к типу, определенному в другой сборке, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.  
  
 **Идентификатор ошибки:** BC30971  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.  
  
2.  В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.  
  
## <a name="see-also"></a>См. также  
 [Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB Практическое руководство: изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Диагностика неработающих ссылок](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)
