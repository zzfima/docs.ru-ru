---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: 4c1be34cf76cfb12ea1e3b3246e9e0bc26199c24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687964"
---
# <a name="-removeintchecks"></a>-removeintchecks
Включает проверка ошибки переполнения для целочисленных операций или отключить.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный параметр. `-removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения. Значение по умолчанию — `-removeintchecks-`.<br /><br /> Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверки на наличие ошибок и выполнения вычислений целое число быстрее. Тем не менее, без проверки ошибок, и если что случается емкости типа данных, неверные результаты могут храниться без возникновения ошибки.|  
  
|Чтобы задать - removeintchecks в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` и отключает проверку переполнения для целочисленных.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
