---
title: "@ (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 219c12e4e3c9b847400f00a135d58506c72d2e7f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-c-compiler-options"></a>@ (параметры компилятора C#)
С помощью параметра @ можно указать файл, содержащий параметры компилятора и файлы исходного кода, которые требуется компилировать.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Аргументы  
 `response_file`  
 Файл, содержащий параметры компилятора и файлы исходного кода, которые требуется компилировать.  
  
## <a name="remarks"></a>Примечания  
 Параметры компилятора и файлы исходного кода будут обрабатываться компилятором таким образом, как если бы они были указаны в командной строке.  
  
 Чтобы задать несколько файлов ответов для компиляции, используйте соответствующее число параметров файла ответов. Например:  
  
```  
@file1.rsp @file2.rsp  
```  
  
 В одной строке файла ответов может содержаться несколько параметров компилятора и файлов исходного кода. Спецификация отдельного параметра компилятора должна размещаться на одной строке и не может разбиваться на несколько строк. В файл ответов можно добавлять комментарии, которые должны начинаться с символа #.  
  
 Указание параметров компилятора в файле ответов аналогично выполнению соответствующих команд из командной строки. Дополнительные сведения см. в разделе [Построение из командной строки](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Компилятор обрабатывает параметры команд в том порядке, в котором они встречаются. Таким образом, аргументы командной строки могут переопределять параметры, заданные ранее в файле ответов. Аналогичным образом, параметры в файле ответов будут переопределять параметры, ранее заданные в командной строке или в других файлах ответов.  
  
 В C# представлен файл csc.rsp, который находится в одном каталоге с файлом csc.exe. Дополнительные сведения о файле csc.rsp см. в разделе [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).  
  
 Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.  
  
## <a name="example"></a>Пример  
 Ниже приведено несколько строк из образца файла ответов:  
  
```console  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)

