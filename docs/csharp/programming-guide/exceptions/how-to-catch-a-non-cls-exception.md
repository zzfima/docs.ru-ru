---
title: "Практическое руководство. Перехват несовместимого с CLS исключения | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
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
ms.openlocfilehash: 3515ecab379a0e910cdd5ba82a4a39b085cc816f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-catch-a-non-cls-exception"></a>Практическое руководство. Перехват несовместимого с CLS исключения
Некоторые языки .NET, включая C++/CLI, позволяют объектам вызывать исключения, которые не являются производными от <xref:System.Exception>. Такие исключения называются *несовместимыми с CLS исключениями* или *необработанными исключениями*. В [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] невозможно вызвать несовместимые с CLS исключения, однако можно перехватить их следующими двумя способами.  
  
-   В блоке `catch (Exception e)` как исключение <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
     По умолчанию сборка [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] перехватывает несовместимые с CLS исключения как заключенные в оболочку. Используйте этот способ, если требуется доступ к исходному исключению, который может осуществляться через свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>. Далее в этом разделе описывается процедура перехвата исключений таким способом.  
  
-   В общем блоке перехвата (блоке перехвата, для которого не указан тип исключения), который помещается после блока `catch (Exception)` или `catch (Exception e)`.  
  
     Используйте этот способ, если требуется выполнить какое-либо действие (например, запись в файл журнала) в ответ на несовместимые с CLS исключения, и вам не нужен доступ к сведениям об исключении. По умолчанию среда CLR создает оболочку для всех исключений. Чтобы отключить этот режим, добавьте этот атрибут уровня сборки в код, как правило, в файле AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### <a name="to-catch-a-non-cls-exception"></a>Перехват несовместимого с CLS исключения  
  
1.  В `catch(Exception e) block` используйте ключевое слово `as` для проверки возможности приведения `e` к <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
2.  Получите доступ к исходному исключению через свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как перехватить несовместимое с CLS исключение, которое было вызвано из библиотеки классов, написанной на C++/CLR. Обратите внимание, что в этом примере клиентскому коду [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] заранее известно, что тип вызываемого исключения — <xref:System.String?displayProperty=fullName>. Свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> можно привести к исходному типу при условии, что этот тип доступен из кода.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md)
