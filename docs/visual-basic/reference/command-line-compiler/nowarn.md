---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005400"
---
# <a name="-nowarn"></a>-nowarn
Отключает возможность компилятора создавать предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`numberList`|Необязательный параметр. Разделенный запятыми список ИДЕНТИФИКАЦИОНных номеров предупреждений, которые компилятор должен подавлять. Если идентификаторы предупреждений не указаны, все предупреждения подавляются.|  
  
## <a name="remarks"></a>Примечания  
 Параметр `-nowarn` приводит к тому, что компилятор не создает предупреждения. Чтобы отключить отдельное предупреждение, укажите идентификатор предупреждения для параметра `-nowarn` после двоеточия. Несколько номеров предупреждений разделяются запятыми.  
  
 Необходимо указать только числовую часть идентификатора предупреждения. Например, если вы хотите отключить BC42024, предупреждение для неиспользуемых локальных переменных укажите `-nowarn:42024`.  
  
 Дополнительные сведения об ИДЕНТИФИКАТОРах предупреждений см. [в разделе Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Установка параметра-unwarn в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Установите флажок **Отключить все предупреждения** , чтобы отключить все предупреждения.<br />     -или-<br />     Чтобы отключить определенное предупреждение, выберите пункт **нет** в раскрывающемся списке рядом с предупреждением.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает предупреждения.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
