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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005226"
---
# <a name="-removeintchecks"></a>-removeintchecks
Включает или выключает проверку переполнения для целочисленных операций.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный параметр. Параметр `-removeintchecks-` приводит к тому, что компилятор проверяет все вычисления целых чисел на наличие ошибок переполнения. Значение по умолчанию — `-removeintchecks-`.<br /><br /> Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверку ошибок и ускоряет вычисление целых чисел. Однако без проверки ошибок и при переполняется ли емкость типа данных, могут быть сохранены неправильные результаты без возникновения ошибки.|  
  
|Установка параметра-ремовеинтчеккс в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Измените значение в поле **Удалить проверки переполнения целых чисел** .|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` и отключает проверку переполнения целых чисел.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
