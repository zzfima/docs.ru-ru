---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 917977d8e5e12c231370ab3c956aca9d96e8a8a8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|`+` &#124; `-`|Необязательный. `/removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения. Значение по умолчанию — `/removeintchecks-`.<br /><br /> Указание `/removeintchecks` или `/removeintchecks+` предотвращает проверку ошибок и осуществлять целочисленные вычисления быстрее. Тем не менее, без проверки ошибок, и если производственные мощности тип данных переполнение, неверные результаты могут храниться без возникновения ошибки.|  
  
|Чтобы задать дополнительные сведения в Visual Studio интегрированной среде разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` и отключает проверку переполнения целое число со знаком.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
