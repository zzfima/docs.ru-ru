---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e83a85e29eb4447f8d3b9dddc4f6ccdbc771b23c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483779"
---
# <a name="-vbruntime"></a>-vbruntime
Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Аргументы  
 \-  
 Выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic.  
  
 \+  
 Скомпилируйте со ссылкой на библиотеку времени выполнения Visual Basic по умолчанию.  
  
 \*  
 Выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic и внедрения основных функциональных возможностей библиотеки времени выполнения Visual Basic в сборку.  
  
 `path`  
 Скомпилируйте со ссылкой на указанную библиотеку (DLL).  
  
## <a name="remarks"></a>Примечания  
 `-vbruntime` Параметр компилятора позволяет указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic. Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения регистрируются на код или языковой конструкции, которые создает вызов вспомогательный класс среды выполнения Visual Basic. (Объект *вспомогательное средство среды выполнения Visual Basic* — это функция, определенная в Microsoft.VisualBasic.dll, которая вызывается во время выполнения для выполнения конкретного семантического языка.)  
  
 `-vbruntime+` Параметр определяет такое же поведение, возникающее, если не `-vbruntime` указан ключ. Можно использовать `-vbruntime+` переопределить предыдущий `-vbruntime` коммутаторов.  
  
 Наибольшее число объектов `My` типа будут недоступны при использовании `-vbruntime-` или `-vbruntime:path` параметры.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Внедрение основные функциональные возможности среды выполнения Visual Basic  
 `-vbruntime*` Вариант позволяет выполнять компиляцию без ссылки на библиотеку времени выполнения. Вместо этого основных функциональных возможностей библиотеки времени выполнения Visual Basic внедренных в сборку пользователя. Этот параметр можно использовать, если приложение выполняется на платформах, не содержащих среда выполнения Visual Basic.  
  
 Внедряются следующие компоненты времени выполнения.  
  
-   Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> Константы  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Константы  
  
-   Некоторые объекты из `My` типа  
  
 Если компиляция выполняется с помощью `-vbruntime*` параметр и код ссылается на элемент из библиотеки среды выполнения Visual Basic не внедряется с основные функциональные возможности, компилятор возвращает ошибку, указывающую, что член недоступен.  
  
## <a name="referencing-a-specified-library"></a>Ссылки на указанную библиотеку  
 Можно использовать `path` аргумент для компиляции со ссылкой на библиотеку настраиваемую среду выполнения вместо библиотеки времени выполнения Visual Basic по умолчанию.  
  
 Если значение `path` равно полный путь к DLL, компилятор будет использовать этот файл как на библиотеку времени выполнения. Если значение `path` аргумент не является полный путь к DLL, компилятор Visual Basic будет сначала искать указанный DLL в текущей папке. Затем будет выполнен поиск по пути, который указан с помощью [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) параметр компилятора. Если `-sdkpath` не используется параметр компилятора, компилятор будет искать идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `-vbruntime` для компиляции со ссылкой на пользовательской библиотеки.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>См. также  
 [Core в Visual Basic — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1](https://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
