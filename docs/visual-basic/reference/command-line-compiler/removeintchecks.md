---
title: "/ removeintchecks | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 8e50200b8755ccc6b1c173024856955f5075b67e
ms.lasthandoff: 03/13/2017

---
# <a name="removeintchecks"></a>/removeintchecks
Включает проверка ошибки переполнения для целочисленных операций или отключить.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный. `/removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения. Значение по умолчанию — `/removeintchecks-`.<br /><br /> Указание `/removeintchecks` или `/removeintchecks+` предотвращает проверку ошибок и позволяют быстрее целочисленные вычисления. Тем не менее, без проверки ошибок, и если производственные мощности тип данных переполнен, неверные результаты могут храниться без возникновения ошибки.|  
  
|Чтобы задать дополнительные сведения в Visual Studio интегрированная среда разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` и отключает проверку ошибок переполнения целое число со знаком.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
