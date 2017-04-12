---
title: "Практическое руководство: определить, является ли файл сборкой (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2e58363369ae4420879310bf09ed89cdd4f5b5cc
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Практическое руководство: определить, является ли файл сборкой (Visual Basic)
Файл является сборкой только в том случае, если он является управляемой и содержит запись сборки в своих метаданных. Дополнительные сведения о сборках и метаданных см. в разделе [манифест сборки](https://msdn.microsoft.com/library/1w45z383).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Как вручную определить, является ли файл сборкой  
  
1.  Запустите [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Загрузите файл, который вы хотите протестировать.  
  
3.  Если **ILDASM** отчеты, что файл не переносимый исполняемый (PE) файл, то он не является сборкой. Дополнительные сведения см. в разделе [Практическое руководство: просмотр содержимого сборки](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Как программно определить, является ли файл сборкой  
  
1.  Вызов <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>метод, указав полный путь к файлу и имя файла, вы тестируете.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
2.  Если <xref:System.BadImageFormatException>исключения, файл не является сборкой.</xref:System.BadImageFormatException>  
  
## <a name="example"></a>Пример  
 В этом примере проверяет библиотеку DLL, является ли сборка.  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>Метод загружает файл теста и освобождает его после считывания информации.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>   
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Сборки и глобальный кэш сборок (Visual Basic)](index.md)
