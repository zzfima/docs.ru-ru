---
title: "How to: Map HRESULTs and Exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interoperation with unmanaged code, HRESULTs"
  - "exceptions, HRESULTs"
  - "interoperation with unmanaged code, exceptions"
  - "HRESULTs"
  - "COM interop, HRESULTs"
  - "COM interop, exceptions"
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Map HRESULTs and Exceptions
COM\-методы сообщают об ошибках, возвращая значения HRESULT. Методы .NET сообщают об ошибках путем создания исключений.  Среда выполнения осуществляет перевод значений HRESULT в исключения и наоборот.  Каждому классу исключений в .NET Framework соответствует значение HRESULT.  
  
 В определенных пользователем классах исключений могут указываться любые подходящие значения HRESULT.  Эти классы исключений могут динамически изменять значения HRESULT и возвращать их при генерации исключения. Для этого нужно заполнить поле **HResult** в объекте исключения.  Дополнительные сведения об исключении предоставляются клиенту через интерфейс **IErrorInfo**, реализованный в объекте .NET в неуправляемом процессе.  
  
 Если создается класс, расширяющий **System.Exception**, во время создания необходимо задать поле HRESULT.  В противном случае значение HRESULT будет присвоено базовым классом.  Новые классы исключения можно сопоставить с существующим значением HRESULT, передав значение в конструктор исключения.  
  
 Обратите внимание, что среда выполнения иногда будет игнорировать `HRESULT`, если в потоке присутствует интерфейс `IErrorInfo`.  Такое поведение может возникать, когда `HRESULT` и `IErrorInfo` представляют разные ошибки.   ``  
  
### Создание нового исключения и сопоставление его с HRESULT  
  
1.  Для создания нового класса исключения с именем `NoAccessException` и сопоставления его значению HRESULT `E_ACCESSDENIED` можно использовать следующий код.  
  
    ```cpp  
    Class NoAccessException : public ApplicationException  
    {  
        NoAccessException () {  
        HResult = E_ACCESSDENIED;   
    }  
    }  
    CMyClass::MethodThatThrows  
    {  
    throw new NoAccessException();  
    }  
    ```  
  
 Существуют программы \(на любом языке программирования\), в которых одновременно используются как управляемый, так и неуправляемый код.  Например, в следующем примере кода настраиваемый упаковщик с помощью метода **Marshal.ThrowExceptionForHR\(int HResult\)** создает исключение с конкретным результатом HRESULT.  Метод просматривает HRESULT и создает соответствующий тип исключения.  Например, значение HRESULT в следующем фрагменте кода создает исключение **ArgumentException**.  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 В следующей таблице приведен полный перечень значений HRESULT, связанных с классами исключений в .NET Framework.  
  
|HRESULT|Исключение .NET|  
|-------------|---------------------|  
|**MSEE\_E\_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR\_E\_APPLICATION**|**ApplicationException**|  
|**COR\_E\_ARGUMENT или E\_INVALIDARG**|**ArgumentException**|  
|**COR\_E\_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR\_E\_ARITHMETIC или ERROR\_ARITHMETIC\_OVERFLOW**|**ArithmeticException**|  
|**COR\_E\_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR\_E\_BADIMAGEFORMAT или ERROR\_BAD\_FORMAT**|**BadImageFormatException**|  
|**COR\_E\_COMEMULATE\_ERROR**|**COMEmulateException**|  
|**COR\_E\_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR\_E\_CORE**|**CoreException**|  
|**NTE\_FAIL**|**CryptographicException**|  
|**COR\_E\_DIRECTORYNOTFOUND или ERROR\_PATH\_NOT\_FOUND**|**DirectoryNotFoundException**|  
|**COR\_E\_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR\_E\_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR\_E\_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR\_E\_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR\_E\_EXCEPTION**|**Исключение**|  
|**COR\_E\_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR\_E\_FIELDACCESS**|**FieldAccessException**|  
|**COR\_E\_FILENOTFOUND или ERROR\_FILE\_NOT\_FOUND**|**FileNotFoundException**|  
|**COR\_E\_FORMAT**|**FormatException**|  
|**COR\_E\_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR\_E\_INVALIDCAST или E\_NOINTERFACE**|**InvalidCastException**|  
|**COR\_E\_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR\_E\_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR\_E\_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR\_E\_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR\_E\_IO**|**IOException**|  
|**COR\_E\_MEMBERACCESS**|**AccessException**|  
|**COR\_E\_METHODACCESS**|**MethodAccessException**|  
|**COR\_E\_MISSINGFIELD**|**MissingFieldException**|  
|**COR\_E\_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR\_E\_MISSINGMEMBER**|**MissingMemberException**|  
|**COR\_E\_MISSINGMETHOD**|**MissingMethodException**|  
|**COR\_E\_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR\_E\_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E\_NOTIMPL**|**NotImplementedException**|  
|**COR\_E\_NOTSUPPORTED**|**NotSupportedException**|  
|**COR\_E\_NULLREFERENCE или E\_POINTER**|**NullReferenceException**|  
|**COR\_E\_OUTOFMEMORY или**<br /><br /> **E\_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR\_E\_OVERFLOW**|**OverflowException**|  
|**COR\_E\_PATHTOOLONG или ERROR\_FILENAME\_EXCED\_RANGE**|**PathTooLongException**|  
|**COR\_E\_RANK**|**RankException**|  
|**COR\_E\_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR\_E\_REMOTING**|**RemotingException**|  
|**COR\_E\_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR\_E\_SECURITY**|**SecurityException**|  
|**COR\_E\_SERIALIZATION**|**SerializationException**|  
|**COR\_E\_STACKOVERFLOW или ERROR\_STACK\_OVERFLOW**|**StackOverflowException**|  
|**COR\_E\_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR\_E\_SYSTEM**|**SystemException**|  
|**COR\_E\_TARGET**|**TargetException**|  
|**COR\_E\_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR\_E\_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR\_E\_THREADABORTED**|**ThreadAbortException**|  
|**COR\_E\_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR\_E\_THREADSTATE**|**ThreadStateException**|  
|**COR\_E\_THREADSTOP**|**ThreadStopException**|  
|**COR\_E\_TYPELOAD**|**TypeLoadException**|  
|**COR\_E\_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR\_E\_VERIFICATION**|**VerificationException**|  
|**COR\_E\_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR\_E\_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**Все остальные значения HRESULT**|**COMException**|  
  
 Чтобы извлечь расширенные сведения об ошибке, управляемый клиент должен проверить поля созданного объекта исключения.  Чтобы объект исключения предоставил нужные сведения об ошибке, COM\-объект должен реализовать интерфейс **IErrorInfo**.  Среда выполнения использует сведения, предоставленные объектом **IErrorInfo**, для инициализации объекта исключения.  
  
 Если COM\-объект не поддерживает интерфейс **IErrorInfo**, среда выполнения инициализирует объект исключения со значениями, использующимися по умолчанию.  В следующей таблице перечислены все поля, связанные с объектом исключения, и указан источник сведений по умолчанию, если COM\-объект поддерживает **IErrorInfo**.  
  
 Обратите внимание, что среда выполнения иногда будет игнорировать `HRESULT`, если в потоке присутствует интерфейс `IErrorInfo`.  Такое поведение может возникать, когда `HRESULT` и `IErrorInfo` представляют разные ошибки.   ``  
  
|Поле исключения|Источник сведений из COM|  
|---------------------|------------------------------|  
|**ErrorCode**|Значение HRESULT, возвращаемое из вызова.|  
|**HelpLink**|Если значение **IErrorInfo\-\>HelpContext** не равно нулю, строка формируется путем объединения **IErrorInfo\-\>GetHelpFile**, "\#" and **IErrorInfo\-\>GetHelpContext**.  В противном случае строка возвращается из **IErrorInfo\-\>GetHelpFile**.|  
|**InnerException**|Всегда пустая ссылка \(**Nothing** в Visual Basic\).|  
|**Сообщение**|Строка, возвращаемая из **IErrorInfo\-\>GetDescription**.|  
|**Исходный код**|Строка возвращается из **IErrorInfo\-\>GetSource**.|  
|**StackTrace**|Трассировка стека.|  
|**TargetSite**|Имя метода, который вернул сбойное значение HRESULT.|  
  
 Поля исключения, такие как **Message**, **Source** и **StackTrace** недоступны для **StackOverflowException**.  
  
## См. также  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ru-ru/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Исключения](../../../docs/standard/exceptions/index.md)