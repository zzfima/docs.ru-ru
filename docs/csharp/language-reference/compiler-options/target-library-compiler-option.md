---
title: "/target:library (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dll
dev_langs:
- CSharp
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
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
ms.openlocfilehash: f739d778e7bada7f34e42ecfd05364e8cae5d453
ms.lasthandoff: 03/13/2017

---
# <a name="targetlibrary-c-compiler-options"></a>/target:library (параметры компилятора C#)
Параметр **/target:library** заставляет компилятор создавать библиотеку динамической компоновки (DLL), а не исполняемый файл (EXE).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/target:library  
```  
  
## <a name="remarks"></a>Примечания  
 Библиотека DLL создается с расширением DLL.  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  
  
 Для создания DLL-файла используются все файлы, указанные в командной строке до следующего параметра **/out** или **/target: module**.  
  
 При построении библиотеки DLL метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md) не требуется.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Перейдите на страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция файла`in.cs`, создание модуля `in.dll`:  
  
```  
csc /target:library in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [/target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
