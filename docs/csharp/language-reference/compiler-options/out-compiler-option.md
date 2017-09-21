---
title: "-out (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /out
dev_langs:
- CSharp
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: 15
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
ms.openlocfilehash: a6db728bc98f5223fc35268a1cce41021ff530cc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="out-c-compiler-options"></a>/out (параметры компилятора C#)
Параметр **/out** задает имя выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/out:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя выходного файла, создаваемого компилятором.  
  
## <a name="remarks"></a>Примечания  
 В командной строке можно указать несколько выходных файлов для компиляции. После параметра компилятора **/out** необходимо указать один или несколько файлов исходного кода. Все указанные файлы исходного кода будут скомпилированы в выходной файл, заданный с помощью параметра **/out**.  
  
 Укажите полное имя и расширение файла, который требуется создать.  
  
 Если имя выходного файла не указано:  
  
-   EXE-файлу будет присвоено имя файла исходного кода, который содержит метод **Main**.  
  
-   DLL-файлы и NETMODULE-файлы берут имя из первого файла исходного кода.  
  
 Файл исходного кода, используемый для компиляции одного выходного файла, не может использоваться в рамках той же компиляции для создания другого выходного файла.  
  
 При создании нескольких выходных файлов путем компиляции из командной строки имейте в виду, что среди выходных файлов только один может быть сборкой. При этом сборкой может быть только первый выходной файл, явно или неявно заданный с помощью параметра **/out**.  
  
 Все модули, созданные в процессе компиляции, будут связаны со сборкой, полученной в результате этого процесса. С помощью [ildasm.exe](https://msdn.microsoft.com/library/f7dy01k1) можно просмотреть связанные файлы в манифесте сборки.  
  
 Параметр компилятора /out обязателен, если требуется установить EXE-файл в качестве целевого для дружественной сборки. Дополнительные сведения см. в разделе [Дружественные сборки](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Перейдите на страницу свойств **Приложение**.  
  
3.  Измените свойство **Имя сборки**.  
  
     Установка этого параметра компилятора программным способом: свойство <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> доступно только для чтения и определяется сочетанием типа проекта (исполняемый файл, библиотека и т. д.) и именем сборки. Чтобы задать имя выходного файла, необходимо изменить одно из этих свойств или одновременно оба свойства.  
  
## <a name="example"></a>Пример  
 Компиляция `t.cs` и создание выходного файла `t.exe`, а также построение `t2.cs` и создание выходного файла модуля `mymodule.netmodule`:  
  
```console  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Дружественные сборки](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

