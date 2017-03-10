---
title: "#pragma checksum (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#pragma checksum"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma checksum [C#]"
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# #pragma checksum (Справочник по C#)
Создание контрольных сумм файл исходного кода для помощи в отладке страниц [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].  
  
## Синтаксис  
  
```  
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### Параметры  
 `"filename"`  
 Имя файла, для которого требуется отслеживание изменений и обновлений.  
  
 `"{guid}"`  
 Идентификатор GUID этого файла.  
  
 `"checksum_bytes"`  
 Шестнадцатеричное значение контрольной суммы.  Должно содержать четное количество шестнадцатеричных чисел.  В случае нечетного количества при компиляции будет показано предупреждение, а директива не будет обработана.  
  
## Заметки  
 Отладчик Visual Studio использует контрольную сумму для проверки правильности исходного кода.  Компилятор вычисляет контрольную сумму для файла исходного кода, затем передает результат в файл PDB базы данных программы.  После этого отладчик использует PDB для сравнения с вычисленной контрольной суммой.  
  
 Это решение не работает для проектов [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)], поскольку контрольная сумма вычисляется для файла исходного кода, а не для ASPX\-файла.  Для решения этой проблемы функция `#pragma checksum` обеспечивает поддержку контрольных сумм для страниц [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].  
  
 При создании проекта [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] в [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] созданный файл исходного кода содержит контрольную сумму для ASPX\-файла, из которого создается файл исходного кода.  Затем компилятор записывает эти данные в файл PDB.  
  
 Если компилятор не находит директивы `#pragma checksum` в файле, он вычислят контрольную сумму и записывает значение в файл PDB.  
  
## Пример  
  
```  
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)