---
title: "/ nowarn | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 61b145a9eb95f5357c7aa2983a96c31e8f2cef6a
ms.lasthandoff: 03/13/2017

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
|`numberList`|Необязательный. Список с разделителями запятыми Идентификационных номеров предупреждений, которые компилятор не должен отображать. Если идентификаторы предупреждений не указаны, то подавляются все предупреждения.|  
  
## <a name="remarks"></a>Примечания  
 `/nowarn` Параметр указывает компилятору не генерировать предупреждения. Для подавления отдельных предупреждений, укажите идентификатор предупреждения для `/nowarn` после двоеточия. Отделите предупреждения друг от друга запятыми.  
  
 Необходимо указать только числовую часть идентификатора предупреждения. Например, если требуется подавить BC42024, предупреждение для неиспользуемых локальных переменных, укажите `/nowarn:42024`.  
  
 Дополнительные сведения об Идентификационных номеров предупреждений см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Установка/nowarn в Visual Studio интегрированная среда разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Выберите **отключить все предупреждения** флажок, чтобы отключить все предупреждения.<br />     -или-<br />     Чтобы отключить определенное предупреждение, щелкните **нет** из раскрывающегося списка рядом с предупреждением.|  
  
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
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Настройка предупреждений в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)
