---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351710"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Приводит к тому, что компилятор обрабатывает первое появление предупреждения как ошибку.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|+ &#124; -|Необязательный. Параметр `-warnaserror-` включен по умолчанию. Предупреждения не препятствуют созданию выходного файла компилятором. Если задан параметр `-warnaserror` или эквивалентный ему `-warnaserror+`, все предупреждения обрабатываются как ошибки.|  
|`numberList`|Необязательный. Разделенный запятыми список с номерами идентификаторов предупреждений, к которому применим параметр `-warnaserror`. Если идентификатор предупреждения не указан, параметр `-warnaserror` применяется ко всем предупреждениям.|  
  
## <a name="remarks"></a>Заметки  
 Параметр `-warnaserror` обрабатывает все предупреждения как ошибки. Все сообщения, которые до этого получали статус предупреждений, будут возвращаться как ошибки. Компилятор сообщает о последующих появлениях того же предупреждения как о предупреждениях.  
  
 Параметр `-warnaserror-` включен по умолчанию, в результате чего предупреждения имеют только информационный характер. Если задан параметр `-warnaserror` или эквивалентный ему `-warnaserror+`, все предупреждения обрабатываются как ошибки.  
  
 Если требуется обрабатывать как ошибки только конкретные предупреждения, укажите их номера через запятую.  
  
> [!NOTE]
> Параметр `-warnaserror` не управляет способом отображения предупреждений. Используйте параметр [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md), чтобы отключить предупреждения.  
  
|Настройка параметра -warnaserror для обработки всех предупреждений как ошибок в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Have a project selected in **Solution Explorer**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Click the **Compile** tab.<br />3.  Make sure the **Disable all warnings** check box is unchecked.<br />4.  Check the **Treat all warnings as errors** check box.|  
  
|Настройка параметра -warnaserror для обработки конкретных предупреждений как ошибок в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Have a project selected in **Solution Explorer**. В меню **Проект** выберите пункт **Свойства**.<br />2.  Click the **Compile** tab.<br />3.  Make sure the **Disable all warnings** check box is unchecked.<br />4.  Make sure the **Treat all warnings as errors** check box is unchecked.<br />5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и настраивает компилятор на отображение ошибки при первом появлении каждого обнаруженного предупреждения.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и обрабатывает как ошибку только предупреждение о неиспользуемых локальных переменных (42024).  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
