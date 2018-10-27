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
ms.openlocfilehash: f061497083dc23fd07f61108938a4129c0af5f3a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188544"
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
|`+` &#124; `-`|Необязательный. `-removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения. Значение по умолчанию — `-removeintchecks-`.<br /><br /> Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверки на наличие ошибок и выполнения вычислений целое число быстрее. Тем не менее, без проверки ошибок, и если что случается емкости типа данных, неверные результаты могут храниться без возникновения ошибки.|  
  
|Чтобы задать - removeintchecks в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` и отключает проверку переполнения для целочисленных.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
