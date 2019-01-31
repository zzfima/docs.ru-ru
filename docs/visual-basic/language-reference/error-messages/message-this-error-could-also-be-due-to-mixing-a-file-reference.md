---
title: <message> Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку <assemblyname>
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: f28327b4df5b15f368f736e7402179227035a06e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272556"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>\<сообщение > Эта ошибка также может быть вызвана смешением ссылки на файл в проект ссылку на сборку "\<имя_сборки >"
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
