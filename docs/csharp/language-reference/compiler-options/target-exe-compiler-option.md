---
title: -target:exe (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 6087a64bea5a59bfcfc5372f6a9d6eb8b9c940cb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606465"
---
# <a name="-targetexe-c-compiler-options"></a>-target:exe (параметры компилятора C#)
Параметр **-target:exe** предписывает компилятору создать исполняемое (EXE) консольное приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр **-target:exe** действует по умолчанию. Исполняемый файл создается с расширением ЕХЕ.  
  
 Используйте параметр [-target:winexe](./target-winexe-compiler-option.md) для создания исполняемого файла программы Windows.  
  
 Если не указано иное с помощью параметра [-out](./out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../programming-guide/main-and-command-args/index.md).  
  
 Для создания EXE-файла используются все файлы, указанные в командной строке до следующего параметра **-out** или **-target:module**.  
  
 В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**. Если код содержит несколько классов с методом **Main**, то указать, какой класс содержит метод **Main**, можно с помощью параметра компилятора [-main](./main-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте страницу **Свойства** проекта.  
  
2. Перейдите на страницу свойств **Приложение**.  
  
3. Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 В каждой из представленных ниже команд командной строки выполняется компиляция файла `in.cs` для создания файла `in.exe`.  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a>См. также

- [-target (параметры компилятора C#)](./target-compiler-option.md)
- [Параметры компилятора C# ](./index.md)
