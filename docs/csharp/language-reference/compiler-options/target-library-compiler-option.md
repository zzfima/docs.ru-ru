---
title: -target:library (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 2e0935965e9225ab524290429803fe4c9ccc80c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313649"
---
# <a name="-targetlibrary-c-compiler-options"></a>-target:library (параметры компилятора C#)
Параметр **-target:library** заставляет компилятор создавать библиотеку динамической компоновки (DLL), а не исполняемый файл (EXE).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a>Примечания  
 Библиотека DLL создается с расширением DLL.  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  
  
 Для создания DLL-файла используются все файлы, указанные в командной строке до следующего параметра **-out** или **-target: module**.  
  
 При построении библиотеки DLL метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md) не требуется.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте страницу **Свойства** проекта.  
  
2. Перейдите на страницу свойств **Приложение**.  
  
3. Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция файла`in.cs`, создание модуля `in.dll`:  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a>См. также

- [-target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
