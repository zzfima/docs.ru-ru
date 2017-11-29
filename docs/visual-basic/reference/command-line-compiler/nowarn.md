---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8da27ea2f9f0a4d370928d70cda1a796b822d97c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nowarn"></a>/nowarn
Отключает возможность компилятора создавать предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`numberList`|Необязательно. Список с разделителями запятыми Идентификационных номеров предупреждений, компилятор не должен отображать. Если идентификаторы предупреждений не указаны, то все предупреждения подавляются.|  
  
## <a name="remarks"></a>Примечания  
 `/nowarn` Заставляет компилятор не создает предупреждений. Для подавления отдельных предупреждений, укажите идентификатор предупреждения для `/nowarn` после двоеточия. Несколько номеров предупреждений следует разделяйте запятыми.  
  
 Необходимо указать числовой частью идентификатора предупреждения. Например, если вы хотите запретить BC42024, предупреждение для неиспользуемых локальных переменных, указать `/nowarn:42024`.  
  
 Дополнительные сведения о Идентификационных номеров предупреждений см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Установка в Visual Studio/nowarn интегрированной среде разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Выберите **отключить все предупреждения** флажок, чтобы отключить все предупреждения.<br />     -или-<br />     Чтобы отключить конкретного предупреждения, щелкните **нет** из раскрывающегося списка рядом с предупреждением.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает все предупреждения.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
