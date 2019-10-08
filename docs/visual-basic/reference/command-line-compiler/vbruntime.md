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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005053"
---
# <a name="-vbruntime"></a>-vbruntime
Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Аргументы  
 \-  
 Скомпилируйте без ссылки на библиотеку времени выполнения Visual Basic.  
  
 \+  
 Скомпилируйте со ссылкой на библиотеку времени выполнения Visual Basic по умолчанию.  
  
 \*  
 Скомпилируйте без ссылки на библиотеку времени выполнения Visual Basic и внедрите основные функции из библиотеки среды выполнения Visual Basic в сборку.  
  
 `path`  
 Скомпилируйте со ссылкой на указанную библиотеку (DLL).  
  
## <a name="remarks"></a>Примечания  
 Параметр компилятора `-vbruntime` позволяет указать, что компилятор должен компилироваться без ссылки на библиотеку времени выполнения Visual Basic. Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения записываются в код или языковые конструкции, которые создают вызов вспомогательного метода среды выполнения Visual Basic. ( *Вспомогательный объект среды выполнения Visual Basic* — это функция, определенная в Microsoft. VisualBasic. dll, которая вызывается во время выполнения для выполнения определенной семантики языка.)  
  
 Параметр `-vbruntime+` дает такое же поведение, которое происходит, если не указан параметр `-vbruntime`. Для переопределения предыдущих параметров `-vbruntime` можно использовать параметр `-vbruntime+`.  
  
 Большинство объектов типа `My` недоступны при использовании параметров `-vbruntime-` или `-vbruntime:path`.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Внедрение основных функций среды выполнения Visual Basic  
 Параметр `-vbruntime*` позволяет компилировать без ссылки на библиотеку времени выполнения. Вместо этого основные функции из библиотеки среды выполнения Visual Basic встраиваются в сборку пользователя. Этот параметр можно использовать, если приложение работает на платформах, которые не содержат Visual Basic среды выполнения.  
  
 Внедряются следующие члены среды выполнения:  
  
- Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
- Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
- Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
- Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbBack>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbCr>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbLf>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbTab>  
  
- Константа <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
- Некоторые объекты типа `My`  
  
 Если компиляция выполняется с параметром `-vbruntime*`, а код ссылается на элемент из библиотеки среды выполнения Visual Basic, который не внедрен в основные функции, компилятор возвращает ошибку, указывающую, что элемент недоступен.  
  
## <a name="referencing-a-specified-library"></a>Ссылка на указанную библиотеку  
 Аргумент `path` можно использовать для компиляции со ссылкой на пользовательскую библиотеку времени выполнения вместо библиотеки среды выполнения по умолчанию Visual Basic.  
  
 Если значение аргумента `path` является полным путем к библиотеке DLL, компилятор будет использовать этот файл в качестве библиотеки времени выполнения. Если значение аргумента `path` не является полным путем к DLL, компилятор Visual Basic будет сначала искать определенную библиотеку DLL в текущей папке. Затем он будет искать по пути, указанному с помощью параметра компилятора [-сдкпас](../../../visual-basic/reference/command-line-compiler/sdkpath.md) . Если параметр компилятора `-sdkpath` не используется, компилятор выполнит поиск идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать параметр `-vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>См. также

- [Visual Basic Core — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1 (SP1)](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
