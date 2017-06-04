---
title: "Иерархия исключений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "типы исключений"
  - "Среда выполнения, исключения"
  - "базовые исключения"
  - "ApplicationException - класс"
  - "Общеязыковая среда выполнения, исключения"
  - "Исключений COM-взаимодействия,"
  - "исключения, иерархий"
ms.assetid: f7d68675-be06-40fb-a555-05f0c5a6f66b
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# Иерархия исключений
Существует два типа исключений: исключения, созданные исполняемой программой, и исключения, созданные средой CLR. Кроме того, существует иерархия исключений, которые могут создаваться приложением или средой выполнения.  
  
 <xref:System.Exception?displayProperty=fullName> класс является базовым классом для исключений. Несколько классов исключений наследуются непосредственно из <xref:System.Exception>, в том числе <xref:System.ApplicationException> и <xref:System.SystemException>. Эти два класса образуют основу для почти всех исключений среды выполнения.  
  
 Большинство исключений, полученных непосредственно из <xref:System.Exception> добавить никаких функций и новых элементов. Например <xref:System.InvalidCastException> иерархия классов имеет следующий вид:  
  
 <xref:System.Object> <xref:System.Exception> <xref:System.SystemException> <xref:System.InvalidCastException>  
  
 Среда выполнения создает соответствующий производный класс <xref:System.SystemException> при обнаружении ошибок. Эти ошибки возникают из завершившихся неудачно проверок во время выполнения (например, массив ошибок "вне диапазона") и могут возникать при выполнении любого метода. Если вы разрабатываете приложение, которое создает новые исключения, такие исключения из следует создавать <xref:System.Exception> класса. Не рекомендуется перехватывать <xref:System.SystemException>, ни хорошим тоном throw <xref:System.SystemException> в приложении.  
  
 Наиболее серьезные исключения — создаются средой выполнения или при наличии условий, включают <xref:System.ExecutionEngineException>, <xref:System.StackOverflowException>, и <xref:System.OutOfMemoryException>.  
  
 Исключения взаимодействия являются производными от <xref:System.SystemException> и еще более расширены с <xref:System.Runtime.InteropServices.ExternalException>. Например <xref:System.Runtime.InteropServices.COMException> исключения, возникшие во время операций COM-взаимодействия и является производным от <xref:System.Runtime.InteropServices.ExternalException>. <xref:System.ComponentModel.Win32Exception> и <xref:System.Runtime.InteropServices.SEHException> также являются производными от <xref:System.Runtime.InteropServices.ExternalException>.  
  
## <a name="hierarchy-of-runtime-exceptions"></a>Иерархия исключений среды выполнения  
 Среда выполнения имеет базовый набор исключений, производных от <xref:System.SystemException> возникает при выполнении отдельных инструкций. В следующей таблице иерархически перечисляются стандартные исключения, предоставляемые средой выполнения, и условия, при которых необходимо создавать производный класс.  
  
|Тип исключения|Базовый тип|Описание|Пример|  
|--------------------|---------------|-----------------|-------------|  
|[Исключение](../../../docs/standard/exceptions/exception-class-and-properties.md)|<xref:System.Object>|Базовый класс для всех исключений.|Отсутствует (используйте производный класс этого исключения).|  
|<xref:System.SystemException>|<xref:System.Exception>|Базовый класс для всех ошибок, созданных средой выполнения.|Отсутствует (используйте производный класс этого исключения).|  
|<xref:System.IndexOutOfRangeException>|<xref:System.SystemException>|Вызывается средой выполнения только при неправильной индексации массива.|Индексирование массива вне допустимого диапазона:<br /><br /> `var i = arr[arr.Length + 1];`<br /><br /> `Dim i = arr(arr.Length + 1)`|  
|<xref:System.NullReferenceException>|<xref:System.SystemException>|Вызывается средой выполнения только в том случае, если имеется ссылка на пустой объект.|`object o = null; string s = o.ToString();`<br /><br /> `Dim o As Object = Nothing Dim s As String = o.ToString()`|  
|<xref:System.AccessViolationException>|<xref:System.SystemException>|Вызывается средой выполнения только в том случае, если осуществляется обращение к недопустимой памяти.|Возникает, когда при взаимодействии с неуправляемым кодом или с небезопасном управляемым кодом используется недопустимый указатель.|  
|<xref:System.InvalidOperationException>|<xref:System.SystemException>|Вызывается методами в недопустимом состоянии.|Вызов перечислителя `GetNext` метод после удаления элемента из коллекции.|  
|<xref:System.ArgumentException>|<xref:System.SystemException>|Базовый класс для всех исключений аргументов.|Отсутствует (используйте производный класс этого исключения).|  
|<xref:System.ArgumentNullException>|<xref:System.ArgumentException>|Вызывается методами, которые не допускают пустой аргумент.|`String s = null; int i = "Calculate".IndexOf(s);`<br /><br /> `Dim s As String = Nothing Dim i As Integer = "Calculate".IndexOf(s)`|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.ArgumentException>|Вызывается методами, проверяющими попадание аргументов в заданный диапазон.|`String s = "string"; s = s.Substring(s.Length + 1);`<br /><br /> `Dim s As String = "string" s = s.Substring(s.Length + 1)`|  
|<xref:System.Runtime.InteropServices.ExternalException>|<xref:System.SystemException>|Базовый класс для исключений, которые возникают или предназначены для сред вне среды выполнения.|Отсутствует (используйте производный класс этого исключения).|  
|<xref:System.Runtime.InteropServices.COMException>|<xref:System.Runtime.InteropServices.ExternalException>|Исключение, инкапсулирующее сведения HRESULT COM.|Используется в COM-взаимодействии.|  
|<xref:System.Runtime.InteropServices.SEHException>|<xref:System.Runtime.InteropServices.ExternalException>|Исключение, инкапсулирующее сведения структурированной обработки исключений Win32.|Используется во взаимодействиях с неуправляемым кодом.|  
  
## <a name="see-also"></a>См. также  
 [Класс Exception и его свойства](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [Основы обработки исключений](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Лучшие методики обработки исключений](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Исключения](../../../docs/standard/exceptions/index.md)