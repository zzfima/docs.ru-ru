---
title: "Использование объектов, реализующих IDisposable"
description: "Использование объектов, реализующих IDisposable"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/19/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: df780a6e-734e-44b8-9747-9f7783f79e20
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 63ad1233b5eab63670fd51f41f86269f643209a7
ms.lasthandoff: 03/02/2017

---

# <a name="using-objects-that-implement-idisposable"></a>Использование объектов, реализующих IDisposable

Сборщик мусора среды CLR освобождает память, используемую неуправляемыми объектами, но типы, которые применяют неуправляемые ресурсы, реализуют интерфейс [IDisposable](xref:System.IDisposable), который позволяет освободить неуправляемую память. По окончании использования объекта, который реализует интерфейс [IDisposable](xref:System.IDisposable), необходимо вызвать реализацию объекта [IDisposable.Dispose](xref:System.IDisposable.Dispose). Это можно сделать одним из двух способов.

* С помощью оператора `using` (C#) или `Using` (Visual Basic).

* Путем реализации блока `try/finally`. 

## <a name="the-using-statement"></a>Оператор using

Операторы `using` (C#) и `Using` (Visual Basic) упрощают составление кода для создания и очистки объекта. Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект. Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы. 

В следующем примере для создания и освобождения объекта [System.IO.StreamReader](xref:System.IO.StreamReader) используется оператор `using`.

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer = new Char[50];
      using (StreamReader s = new StreamReader("File1.txt")) {
         int charsRead = 0;
         while (s.Peek() != -1) {
            charsRead = s.Read(buffer, 0, buffer.Length);
            //
            // Process characters read.
            //   
         }
         s.Close();    
      }

   }
}
```

```vb
Imports System.IO

Module Example
   Public Sub Main()
      Dim buffer(49) As Char
      Using s As New StreamReader("File1.txt")
         Dim charsRead As Integer
         Do While s.Peek() <> -1
            charsRead = s.Read(buffer, 0, buffer.Length)         
            ' 
            ' Process characters read.
            '
         Loop
         s.Close()
      End Using
   End Sub
End Module
```

Обратите внимание, что хотя класс [StreamReader](xref:System.IO.StreamReader) реализует интерфейс [IDisposable](xref:System.IDisposable), который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод [StreamReader.Dispose](xref:System.IO.StreamReader.Dispose(System.Boolean)). Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`. 

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer = new Char[50];
      {
         StreamReader s = new StreamReader("File1.txt"); 
         try {
            int charsRead = 0;
            while (s.Peek() != -1) {
               charsRead = s.Read(buffer, 0, buffer.Length);
               //
               // Process characters read.
               //   
            }
            s.Close();
         }
         finally {
            if (s != null)
               ((IDisposable)s).Dispose();     
         }       
      }
   }
}
```

```vb
Imports System.IO

Module Example
   Public Sub Main()
      Dim buffer(49) As Char
''      Dim s As New StreamReader("File1.txt")
With s As New StreamReader("File1.txt")
      Try
         Dim charsRead As Integer
         Do While s.Peek() <> -1
            charsRead = s.Read(buffer, 0, buffer.Length)         
            ' 
            ' Process characters read.
            '
         Loop
         s.Close()
      Finally
         If s IsNot Nothing Then DirectCast(s, IDisposable).Dispose()
      End Try
End With
   End Sub
End Module
```

Оператор `using` в C# позволяет присоединять несколько ресурсов в одном операторе, что эквивалентно использованию вложенных инструкций using. В следующем примере создается два объекта [StreamReader](xref:System.IO.StreamReader) для чтения содержимого двух разных файлов. 

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer1 = new Char[50], buffer2 = new Char[50];

      using (StreamReader version1 = new StreamReader("file1.txt"),
                          version2 = new StreamReader("file2.txt")) {
         int charsRead1, charsRead2 = 0;
         while (version1.Peek() != -1 && version2.Peek() != -1) {
            charsRead1 = version1.Read(buffer1, 0, buffer1.Length);
            charsRead2 = version2.Read(buffer2, 0, buffer2.Length);
            //
            // Process characters read.
            //
         }
         version1.Close();
         version2.Close();
      }
   }
}
```

## <a name="tryfinally-block"></a>Блок try/finally

Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую. Это может быть личным стилем программирования или же осуществляться по одной из следующих причин: 

* Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`. В противном случае исключения, вызываемые оператором `using`, а также создаваемые в блоке `using`, если блок `try/catch` отсутствует, не обрабатываются. 

* Чтобы создать экземпляр объекта, реализующего интерфейс [IDisposable](xref:System.IDisposable), область действия которого не является локальной для блока, в котором он объявлен. 

Следующий пример похож на предыдущий с тем отличием, что в нем используется блок `try/catch/finally` для создания экземпляра, использования и удаления объекта [StreamReader](xref:System.IO.StreamReader), а также для обработки исключений, вызываемых конструктором [StreamReader](xref:System.IO.StreamReader) и его методом [ReadToEnd](xref:System.IO.StreamReader.ReadToEnd). Обратите внимание, что перед вызовом метода [Dispose](xref:System.IDisposable.Dispose) код в блоке `finally` проверяет, имеет ли объект, реализующий интерфейс [IDisposable](xref:System.IDisposable), значение `null`. Если этого сделать не удастся, это может привести к исключению [NullReferenceException](xref:System.NullReferenceException) во время выполнения. 

```cs
using System;
using System.Globalization;
using System.IO;

public class Example
{
   public static void Main()
   {
      StreamReader sr = null;
      try {
         sr = new StreamReader("file1.txt");
         String contents = sr.ReadToEnd();
         sr.Close();
         Console.WriteLine("The file has {0} text elements.", 
                           new StringInfo(contents).LengthInTextElements);    
      }      
      catch (FileNotFoundException) {
         Console.WriteLine("The file cannot be found.");
      }   
      catch (IOException) {
         Console.WriteLine("An I/O error has occurred.");
      }
      catch (OutOfMemoryException) {
         Console.WriteLine("There is insufficient memory to read the file.");   
      }
      finally {
         if (sr != null) sr.Dispose();     
      }
   }
}
```

```vb
Imports System.Globalization
Imports System.IO

Module Example
   Public Sub Main()
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader("file1.txt")
         Dim contents As String = sr.ReadToEnd()
         sr.Close()
         Console.WriteLine("The file has {0} text elements.", 
                           New StringInfo(contents).LengthInTextElements)    
      Catch e As FileNotFoundException
         Console.WriteLine("The file cannot be found.")
      Catch e As IOException
         Console.WriteLine("An I/O error has occurred.")
      Catch e As OutOfMemoryException
         Console.WriteLine("There is insufficient memory to read the file.")   
      Finally 
         If sr IsNot Nothing Then sr.Dispose()     
      End Try
   End Sub
End Module
```

Можно следовать этому простому шаблону, если необходимо реализовать блок `try/finally`, поскольку язык программирования не поддерживает оператор `using`, но разрешает прямые вызовы метода [Dispose](xref:System.IDisposable.Dispose). 

## <a name="see-also"></a>См. также

[Очистка неуправляемых ресурсов](unmanaged.md)



