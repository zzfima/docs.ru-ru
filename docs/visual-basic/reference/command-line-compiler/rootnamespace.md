---
title: "/ rootnamespace | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
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
ms.openlocfilehash: 7b261efeb829a6c0b035d7364c63074412a91c7f
ms.lasthandoff: 03/13/2017

---
# <a name="rootnamespace"></a>/rootnamespace
Задает пространство имен для всех объявлений типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`namespace`|Имя пространства имен, в котором находятся все объявления типов для текущего проекта.|  
  
## <a name="remarks"></a>Примечания  
 При использовании исполняемого файла Visual Studio (Devenv.exe) для компиляции проекта, созданного в среде разработки Visual Studio, используйте `/rootnamespace` для указания значения <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>свойство.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> В разделе [командной строки devenv](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) подробнее.  
  
 Использование среды CLR дизассемблер MSIL (я`ldasm.exe`) для просмотра имен пространств имен в выходном файле.  
  
|Чтобы задать дополнительные сведения в Visual Studio интегрированная среда разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в **корневое пространство имен** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и помещает все объявления типов в пространстве имен `mynamespace`.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
