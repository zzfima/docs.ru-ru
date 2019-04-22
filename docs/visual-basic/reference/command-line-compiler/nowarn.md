---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828216"
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
|`numberList`|Необязательный параметр. Разделенный запятыми список номеров предупреждений идентификатор, который компилятор не должен отображать. Если идентификаторы предупреждений не указаны, подавляются все предупреждения.|  
  
## <a name="remarks"></a>Примечания  
 `-nowarn` Предписывает компилятору не создавать предупреждения. Чтобы подавить предупреждение об отдельных, укажите идентификатор предупреждения для `-nowarn` после двоеточия. Разделяйте предупреждения запятыми.  
  
 Необходимо указать только числовую часть идентификатора предупреждения. Например, если вы хотите отключить BC42024, предупреждение для неиспользуемые локальные переменные, укажите `-nowarn:42024`.  
  
 Дополнительные сведения об Идентификационных номеров предупреждений, см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Чтобы задать - nowarn в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Выберите **выключить все предупреждения** флажок, чтобы отключить все предупреждения.<br />     -или-<br />     Чтобы отключить конкретного предупреждения, щелкните **None** из раскрывающегося списка рядом с предупреждением.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает все предупреждения.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемые локальные переменные (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
