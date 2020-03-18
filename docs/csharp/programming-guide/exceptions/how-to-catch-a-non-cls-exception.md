---
title: Практическое руководство. Перехват несовместимого с CLS исключения
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 635cf0a9142f56dea4b2722fbf3f3eda505d85ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75346278"
---
# <a name="how-to-catch-a-non-cls-exception"></a>Практическое руководство. Перехват несовместимого с CLS исключения
Некоторые языки .NET, включая C++/CLI, позволяют объектам вызывать исключения, которые не являются производными от <xref:System.Exception>. Такие исключения называются *несовместимыми с CLS исключениями* или *необработанными исключениями*. В C# невозможно вызвать несовместимые с CLS исключения, однако можно перехватить их следующими двумя способами.  
  
- В блоке `catch (RuntimeWrappedException e)`.
  
     По умолчанию сборка Visual C# перехватывает несовместимые с CLS исключения как заключенные в оболочку. Этот метод следует использовать, если требуется доступ к исходному исключению, который можно получить с помощью свойства <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>. Далее в этом разделе описывается процедура перехвата исключений таким способом.  
  
- В общем блоке перехвата (блоке перехвата, для которого не указан тип исключения), который помещается после остальных блоков `catch`.
  
     Используйте этот способ, если требуется выполнить какое-либо действие (например, запись в файл журнала) в ответ на несовместимые с CLS исключения, и вам не нужен доступ к сведениям об исключении. По умолчанию среда CLR создает оболочку для всех исключений. Чтобы отключить этот режим, добавьте этот атрибут уровня сборки в код, как правило, в файле AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### <a name="to-catch-a-non-cls-exception"></a>Перехват несовместимого с CLS исключения  
  
В блоке `catch(RuntimeWrappedException e)` для доступа к исходному исключению используйте свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как перехватить несовместимое с CLS исключение, которое было вызвано из библиотеки классов, написанной на C++/CLI. Обратите внимание, что в этом примере клиентскому коду C# заранее известно, что тип вызываемого исключения — <xref:System.String?displayProperty=nameWithType>. Можно привести свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> к его исходному типу, если этот тип доступен из кода.  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [Исключения и обработка исключений](./index.md)
