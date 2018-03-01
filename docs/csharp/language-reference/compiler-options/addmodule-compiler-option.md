---
title: "-addmodule (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db440b58862e372e443c9c51961b0c3cc2dd211e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (параметры компилятора C#)
Установка этого параметра приводит к добавлению модуля, созданного с помощью параметра target:module для текущей компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`, `file2`  
 Выходной файл, содержащий метаданные. В данный файл не может входить манифест сборки. Чтобы импортировать несколько файлов, разделите их имена запятыми или точками с запятой.  
  
## <a name="remarks"></a>Примечания  
 Все модули, добавленные с помощью **-addmodule**, во время выполнения должны находиться в том же каталоге, что и выходной файл. То есть во время компиляции можно указать модуль в любом каталоге, но во время выполнения он должен находиться в каталоге приложения. Если во время выполнения модуль отсутствует в каталоге приложения, возникнет <xref:System.TypeLoadException>.  
  
 `file` не может содержать сборку. Например, если выходной файл был создан с помощью [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), для импорта его метаданных можно использовать **-addmodule**.  
  
 Если выходной файл был создан с помощью параметра **-target**, отличного от **-target:module**, для импорта его метаданных запрещено использовать **-addmodule**, но можно [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Этот параметр компилятора недоступен в Visual Studio; проект не может ссылаться на модуль. Кроме того, этот параметр компилятора нельзя изменить программным способом.  
  
## <a name="example"></a>Пример  
 Скомпилируйте исходный файл `input.cs` и добавьте метаданные из `metad1.netmodule` и `metad2.netmodule`, чтобы создать `out.exe`.  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)  
 [Многофайловые сборки](../../../framework/app-domains/multifile-assemblies.md)  
 [Практическое руководство. Создание многофайловой сборки](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
