---
title: '&lt;сообщение&gt; Эта ошибка также может быть вызвана смешением ссылки на файл в проект ссылку на сборку &#39; &lt;имя_сборки&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: d4fb2a8985a21ecea5056b83d2766e8dc468180d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528996"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;сообщение&gt; Эта ошибка также может быть вызвана смешением ссылки на файл в проект ссылку на сборку &#39; &lt;имя_сборки&gt;&#39;
\<сообщение > Эта ошибка также может быть вызвана смешением ссылки на файл в проект ссылку на сборку "\<assemblyname >. В этом случае попробуйте заменить ссылку на файл "\<имя_файла_сборки >" в проекте "\<имя_проекта1 >" со ссылкой проекта "\<имя_проекта2 >".  
  
 Код в проекте обращается к члену другого проекта, но конфигурация решения не позволяет компилятору Visual Basic разрешить ссылку.  
  
 Чтобы получить доступ к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.  
  
 **Идентификатор ошибки:** BC30971  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.  
  
2.  В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.  
  
## <a name="see-also"></a>См. также
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
- [Диагностика неработающих ссылок](/visualstudio/ide/troubleshooting-broken-references)
