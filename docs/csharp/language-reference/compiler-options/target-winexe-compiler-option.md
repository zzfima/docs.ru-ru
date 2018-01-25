---
title: "-target:winexe (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b13af4e665a2bf5a75472bc8f4a501e90c59281a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-targetwinexe-c-compiler-options"></a>-target:winexe (параметры компилятора C#)
Параметр **-target:winexe** предписывает компилятору создать исполняемый файл (EXE), программу Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Примечания  
 Исполняемый файл создается с расширением ЕХЕ. Программа Windows предоставляет пользовательский интерфейс либо из библиотеки .NET Framework, либо с помощью API Win32.  
  
 Воспользуйтесь параметром [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), чтобы создать консольное приложение.  
  
 Если не указано иное с помощью параметра [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Для создания DLL-файла используются все файлы, указанные в командной строке вплоть до следующего параметра **-out** или [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).  
  
 В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**. Параметр [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) позволяет указывать класс, содержащий метод **Main**, в случаях, когда код содержит несколько классов с методом **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Перейдите на страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция `in.cs` в программу Windows:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [-target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
