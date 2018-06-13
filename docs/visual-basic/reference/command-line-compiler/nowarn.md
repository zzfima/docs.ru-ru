---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 338b4672d215968275c30d37a2f8061e764aed8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653446"
---
# <a name="-nowarn"></a>-nowarn
Отключает возможность компилятора создавать предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`numberList`|Необязательный. Список с разделителями запятыми Идентификационных номеров предупреждений, компилятор не должен отображать. Если идентификаторы предупреждений не указаны, то все предупреждения подавляются.|  
  
## <a name="remarks"></a>Примечания  
 `-nowarn` Заставляет компилятор не создает предупреждений. Для подавления отдельных предупреждений, укажите идентификатор предупреждения для `-nowarn` после двоеточия. Несколько номеров предупреждений следует разделяйте запятыми.  
  
 Необходимо указать числовой частью идентификатора предупреждения. Например, если вы хотите запретить BC42024, предупреждение для неиспользуемых локальных переменных, указать `-nowarn:42024`.  
  
 Дополнительные сведения о Идентификационных номеров предупреждений см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Чтобы задать - nowarn в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Выберите **отключить все предупреждения** флажок, чтобы отключить все предупреждения.<br />     -или-<br />     Чтобы отключить конкретного предупреждения, щелкните **нет** из раскрывающегося списка рядом с предупреждением.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает все предупреждения.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
