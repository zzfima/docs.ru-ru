---
title: "-target:exe (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /exe
dev_langs:
- CSharp
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 12
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9d5784186f564241c896333d518e297c3c094f28
ms.lasthandoff: 03/13/2017

---
# <a name="targetexe-c-compiler-options"></a>/target:exe (параметры компилятора C#)
Параметр **/target:exe** предписывает компилятору создать исполняемое (EXE) консольное приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/target:exe  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр **/target:exe** действует по умолчанию. Исполняемый файл создается с расширением ЕХЕ.  
  
 Используйте параметр [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) для создания исполняемого файла программы Windows.  
  
 Если не указано иное с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Для создания EXE-файла используются все файлы, указанные в командной строке до следующего параметра **/out** или **/target:module**.  
  
 В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**. Если код содержит несколько классов с методом **Main**, то указать, какой класс содержит метод **Main**, можно с помощью параметра компилятора [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Перейдите на страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 В каждой из представленных ниже команд командной строки выполняется компиляция файла `in.cs` для создания файла `in.exe`.  
  
```  
csc /target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [/target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
