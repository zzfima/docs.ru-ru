---
title: "Практическое руководство. Перехват несовместимого с CLS исключения | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "исключения [C#], несовместимый с CLS"
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# Практическое руководство. Перехват несовместимого с CLS исключения
Некоторые языки .NET, включая C\+\+\/CLI, позволяют вызывать исключения, которые не являются производными от <xref:System.Exception>.  Такие исключения называются *несовместимыми с CLS исключениями* или *несовместимыми исключениями*.  В [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] невозможно вызвать несовместимое с CLS исключение, однако такое исключение можно перехватить следующими двумя способами.  
  
-   В блоке `catch (Exception e)` как <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
     По умолчанию сборка [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] перехватывает несовместимые с CLS исключения как упакованные исключения.  Данный метод используется, если требуется получить доступ к оригинальному исключению, которое доступно через свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.  Процедура, приведенная далее в этом разделе, описывает перехват исключений данным способом.  
  
-   В блоке общего перехвата \(это блок перехвата, для которого не указан тип исключения\), который помещается после блока `catch (Exception)` или `catch (Exception e)`.  
  
     Данный метод используется, если требуется выполнить какое\-либо действие \(например, произвести запись в файл журнала\) в ответ на несовместимое с CLS исключение, а доступ к сведениям об исключении не требуется.  По умолчанию среда CLR упаковывает все исключения.  Чтобы запретить это поведение, добавьте следующий атрибут уровня сборки в код \(обычно атрибут добавляют в файл AssemblyInfo.cs\): `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### Чтобы перехватить несовместимое с CLS исключение  
  
1.  В `catch(Exception e) block` используйте ключевое слово `as`, чтобы проверить, можно ли привести `e` к <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
2.  Обратитесь к оригинальному исключению, используя свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.  
  
## Пример  
 В следующем примере показан перехват несовместимого с CLS исключения, которое было вызвано из библиотеки классов, написанной на C\+\+\/CLR.  Обратите внимание, что в этом примере коду клиента [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] заранее известно, что вызывается исключение типа <xref:System.String?displayProperty=fullName>.  Свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> можно привести к оригинальному типу при условии, что этот тип доступен из кода.  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## См. также  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)