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
ms.openlocfilehash: d28d0556a662099e4e5e74b22583fc3c8b4c313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-vbruntime"></a>-vbruntime
Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Аргументы  
 \-  
 Компиляцию без ссылки на библиотеку времени выполнения Visual Basic.  
  
 \+  
 Компиляция со ссылкой на значение по умолчанию библиотеки времени выполнения Visual Basic.  
  
 \*  
 Компиляцию без ссылки на библиотеку времени выполнения Visual Basic и внедрения в сборку базовую функциональность библиотеки времени выполнения Visual Basic.  
  
 `path`  
 Компиляция со ссылкой на указанную библиотеку (DLL).  
  
## <a name="remarks"></a>Примечания  
 `-vbruntime` Параметр компилятора позволяет указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic. Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения регистрируются в код или языковой конструкции, которые создает вызов вспомогательный среды выполнения Visual Basic. (A *Вспомогательная среда выполнения Visual Basic* является функция, определенная в Microsoft.VisualBasic.dll, которая вызывается во время выполнения, чтобы выполнить конкретную семантику языка.)  
  
 `-vbruntime+` Же поведение, которое возникает, если он не создает параметр `-vbruntime` указан ключ. Можно использовать `-vbruntime+` могут переопределить предыдущих `-vbruntime` коммутаторов.  
  
 Большинство объектов `My` тип недоступны при использовании `-vbruntime-` или `-vbruntime:path` параметры.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Внедрение основных функциональных возможностей среды выполнения Visual Basic  
 `-vbruntime*` Позволяет компилировать без ссылки на библиотеку времени выполнения. Вместо этого основные функции из библиотеки времени выполнения Visual Basic внедренных в сборку пользователя. Этот параметр можно использовать, если приложение работает на платформах, которые не содержат среда выполнения Visual Basic.  
  
 Внедряются следующие компоненты времени выполнения.  
  
-   Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> Константа  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Константа  
  
-   Некоторые объекты `My` типа  
  
 Если компиляция выполняется с помощью `-vbruntime*` параметр и код ссылается на элемент из библиотеки среды выполнения Visual Basic, не внедрены в основных функциональных возможностей, компилятор возвращает ошибку, указывающую, что член недоступен.  
  
## <a name="referencing-a-specified-library"></a>Создание ссылок на указанную библиотеку  
 Можно использовать `path` аргумент для компиляции со ссылкой на библиотеку времени выполнения пользовательского вместо значения по умолчанию библиотеки времени выполнения Visual Basic.  
  
 Если значение `path` аргумент — полный путь к DLL-файлу, компилятор будет использовать этот файл как библиотеку среды выполнения. Если значение `path` аргумент не является полный путь к библиотеке DLL, компилятор Visual Basic будет сначала искать идентифицированной библиотеки DLL в текущей папке. Затем будет выполнен поиск по пути, указанному с помощью [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) параметр компилятора. Если `-sdkpath` не используется параметр компилятора, компилятор будет искать идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `-vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>См. также  
 [Основные Visual Basic — новый режим компиляции в Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
