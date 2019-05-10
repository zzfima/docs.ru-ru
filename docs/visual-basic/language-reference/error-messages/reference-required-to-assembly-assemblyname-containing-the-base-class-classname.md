---
title: Требуется ссылка на сборку <assemblyname>, содержащую базовый класс <classname>
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 8218a3325d5d47bf85aacab1724221d233d92ba4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661706"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>Требуется ссылка на сборку "\<имя_сборки >" содержит базовый класс\<имя_класса > "
Требуется ссылка на сборку "\<имя_сборки >" содержит базовый класс\<имя_класса > ". Добавьте эту ссылку в проект.  
  
 Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки. Компилятор Visual Basic требует ссылку, чтобы исключить неоднозначность в случае, если класс определен в нескольких библиотеках DLL или сборках.  
  
 **Идентификатор ошибки:** BC30007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.  
  
## <a name="see-also"></a>См. также

- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Диагностика неработающих ссылок](/visualstudio/ide/troubleshooting-broken-references)
