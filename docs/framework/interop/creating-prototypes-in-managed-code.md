---
title: "Создание прототипов в управляемом коде"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- prototypes in managed code
- COM interop, DLL functions
- unmanaged functions
- platform invoke, creating prototypes
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, object fields
- DLL functions
- object fields in platform invoke
ms.assetid: ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a85da0d1714c263b446c88b7c18e934817aea94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-prototypes-in-managed-code"></a><span data-ttu-id="b1bf0-102">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="b1bf0-102">Creating Prototypes in Managed Code</span></span>
<span data-ttu-id="b1bf0-103">В этом разделе описывается доступ к неуправляемым функциям и представлено несколько полей атрибутов, которые уточняют определение метода в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-103">This topic describes how to access unmanaged functions and introduces several attribute fields that annotate method definition in managed code.</span></span> <span data-ttu-id="b1bf0-104">Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="b1bf0-104">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
 <span data-ttu-id="b1bf0-105">Чтобы обратиться к неуправляемой функции DLL из управляемого кода, нужно знать ее имя и имя библиотеки DLL, которая ее экспортирует.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-105">Before you can access an unmanaged DLL function from managed code, you need to know the name of the function and the name of the DLL that exports it.</span></span> <span data-ttu-id="b1bf0-106">Имея эту информацию, можно приступать к написанию управляемого определения для неуправляемой функции, реализованной в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-106">With this information, you can begin to write the managed definition for an unmanaged function that is implemented in a DLL.</span></span> <span data-ttu-id="b1bf0-107">Кроме того, можно настроить способ, которым вызов неуправляемого кода создает функцию и маршалирует данные в функцию и обратно.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-107">Furthermore, you can adjust the way that platform invoke creates the function and marshals data to and from the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1bf0-108">Функции Win32 API, которые распределяют строку, позволяют освободить строку с помощью такого метода, как `LocalFree`.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-108">Win32 API functions that allocate a string enable you to free the string by using a method such as `LocalFree`.</span></span> <span data-ttu-id="b1bf0-109">Вызов неуправляемого кода обрабатывает эти параметры иначе.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-109">Platform invoke handles such parameters differently.</span></span> <span data-ttu-id="b1bf0-110">Для вызовов неуправляемого кода следует использовать параметр типа `IntPtr`, а не `String`.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-110">For platform invoke calls, make the parameter an `IntPtr` type instead of a `String` type.</span></span> <span data-ttu-id="b1bf0-111">Чтобы вручную преобразовать тип в строку и вручную освободить его, можно использовать методы, предоставленные классом <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-111">Use methods that are provided by the <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> class to convert the type to a string manually and free it manually.</span></span>  
  
## <a name="declaration-basics"></a><span data-ttu-id="b1bf0-112">Основы объявления</span><span class="sxs-lookup"><span data-stu-id="b1bf0-112">Declaration Basics</span></span>  
 <span data-ttu-id="b1bf0-113">Как показано в примерах ниже, управляемые определения неуправляемых функций зависят от используемого языка.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-113">Managed definitions to unmanaged functions are language-dependent, as you can see in the following examples.</span></span> <span data-ttu-id="b1bf0-114">Более полные примеры кода представлены в разделе [Примеры вызовов неуправляемого кода](../../../docs/framework/interop/platform-invoke-examples.md).</span><span class="sxs-lookup"><span data-stu-id="b1bf0-114">For more complete code examples, see [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, _  
        ByVal txt As String, ByVal caption As String, _  
        ByVal Typ As Integer) As IntPtr  
End Class  
```  
  
 <span data-ttu-id="b1bf0-115">Для применения полей <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> или <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar> к объявлению [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] необходимо использовать атрибут <xref:System.Runtime.InteropServices.DllImportAttribute> вместо оператора `Declare`.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-115">To apply the <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>, or <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar> fields to a [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] declaration, you must use the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute instead of the `Declare` statement.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
Public Class Win32  
   <DllImport ("user32.dll", CharSet := CharSet.Auto)> _  
   Public Shared Function MessageBox (ByVal hWnd As Integer, _  
        ByVal txt As String, ByVal caption As String, _  
        ByVal Typ As Integer) As IntPtr  
   End Function  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[DllImport("user32.dll")]  
    public static extern IntPtr MessageBox(int hWnd, String text,   
                                       String caption, uint type);  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
[DllImport("user32.dll")]  
    extern "C" IntPtr MessageBox(int hWnd, String* pText,  
    String* pCaption unsigned int uType);  
```  
  
## <a name="adjusting-the-definition"></a><span data-ttu-id="b1bf0-116">Настройка определения</span><span class="sxs-lookup"><span data-stu-id="b1bf0-116">Adjusting the Definition</span></span>  
 <span data-ttu-id="b1bf0-117">Поля атрибутов, заданные явно или неявно, определяют выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-117">Whether you set them explicitly or not, attribute fields are at work defining the behavior of managed code.</span></span> <span data-ttu-id="b1bf0-118">Вызов неуправляемого кода выполняется в соответствии с набором значений по умолчанию различных полей, хранящихся в сборке как метаданные.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-118">Platform invoke operates according to the default values set on various fields that exist as metadata in an assembly.</span></span> <span data-ttu-id="b1bf0-119">Это поведение по умолчанию можно изменить, настроив значения одного или нескольких полей.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-119">You can alter this default behavior by adjusting the values of one or more fields.</span></span> <span data-ttu-id="b1bf0-120">Во многих случаях для установки значения используется <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-120">In many cases, you use the <xref:System.Runtime.InteropServices.DllImportAttribute> to set a value.</span></span>  
  
 <span data-ttu-id="b1bf0-121">Ниже приведен полный набор полей атрибутов, относящихся к вызову неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-121">The following table lists the complete set of attribute fields that pertain to platform invoke.</span></span> <span data-ttu-id="b1bf0-122">Для каждого поля в таблице указано значение по умолчанию и дана ссылка на инструкцию по использованию поля для определения неуправляемых функций DLL.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-122">For each field, the table includes the default value and a link to information on how to use these fields to define unmanaged DLL functions.</span></span>  
  
|<span data-ttu-id="b1bf0-123">Поле</span><span class="sxs-lookup"><span data-stu-id="b1bf0-123">Field</span></span>|<span data-ttu-id="b1bf0-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="b1bf0-124">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|<span data-ttu-id="b1bf0-125">Включает или отключает наилучшее сопоставление.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-125">Enables or disables best-fit mapping.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|<span data-ttu-id="b1bf0-126">Задает соглашение о вызовах, которое должно использоваться при передаче аргументов методов.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-126">Specifies the calling convention to use in passing method arguments.</span></span> <span data-ttu-id="b1bf0-127">Значение по умолчанию — `WinAPI`, что соответствует режиму `__stdcall` для 32-разрядных платформ на базе процессора Intel.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-127">The default is `WinAPI`, which corresponds to `__stdcall` for the 32-bit Intel-based platforms.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|<span data-ttu-id="b1bf0-128">Управляет декорированием имен и способом маршалинга строковых аргументов в функцию.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-128">Controls name mangling and the way that string arguments should be marshaled to the function.</span></span> <span data-ttu-id="b1bf0-129">Значение по умолчанию — `CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-129">The default is `CharSet.Ansi`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|<span data-ttu-id="b1bf0-130">Указывает точку входа DLL для вызова.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-130">Specifies the DLL entry point to be called.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|<span data-ttu-id="b1bf0-131">Определяет, должна ли изменяться точка входа в соответствии с кодировкой.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-131">Controls whether an entry point should be modified to correspond to the character set.</span></span> <span data-ttu-id="b1bf0-132">Значение по умолчанию зависит от языка программирования.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-132">The default value varies by programming language.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|<span data-ttu-id="b1bf0-133">Определяет, должна ли сигнатура управляемого метода преобразовываться в неуправляемую сигнатуру, которая возвращает значение HRESULT и имеет дополнительный аргумент [out, retval] для возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-133">Controls whether the managed method signature should be transformed into an unmanaged signature that returns an HRESULT and has an additional [out, retval] argument for the return value.</span></span><br /><br /> <span data-ttu-id="b1bf0-134">Значение по умолчанию — `true` (сигнатура не должна преобразовываться).</span><span class="sxs-lookup"><span data-stu-id="b1bf0-134">The default is `true` (the signature should not be transformed).</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|<span data-ttu-id="b1bf0-135">Позволяет вызывающему объекту использовать функцию интерфейса API `Marshal.GetLastWin32Error` для определения факта ошибки при выполнении метода.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-135">Enables the caller to use the `Marshal.GetLastWin32Error` API function to determine whether an error occurred while executing the method.</span></span> <span data-ttu-id="b1bf0-136">В Visual Basic значение по умолчанию — `true`, а в C# и C++ — `false`.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-136">In Visual Basic, the default is `true`; in C# and C++, the default is `false`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|<span data-ttu-id="b1bf0-137">Управляет возникновением исключения при появлении несопоставимого символа Юникода, который преобразуется в символ ANSI "?".</span><span class="sxs-lookup"><span data-stu-id="b1bf0-137">Controls throwing of an exception on an unmappable Unicode character that is converted to an ANSI "?" character.</span></span>|  
  
 <span data-ttu-id="b1bf0-138">Дополнительные справочные сведения см. в разделе <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-138">For detailed reference information, see <xref:System.Runtime.InteropServices.DllImportAttribute>.</span></span>  
  
## <a name="platform-invoke-security-considerations"></a><span data-ttu-id="b1bf0-139">Вопросы безопасности при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="b1bf0-139">Platform invoke security considerations</span></span>  
 <span data-ttu-id="b1bf0-140">Члены `Assert`, `Deny` и `PermitOnly` перечисления <xref:System.Security.Permissions.SecurityAction> называются *модификаторами обхода стека*.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-140">The `Assert`, `Deny`, and `PermitOnly` members of the <xref:System.Security.Permissions.SecurityAction> enumeration are referred to as *stack walk modifiers*.</span></span> <span data-ttu-id="b1bf0-141">Эти члены игнорируются, если они используются как декларативные атрибуты в объявлениях вызова неуправляемого кода и операторах COM языка IDL.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-141">These members are ignored if they are used as declarative attributes on platform invoke declarations and COM Interface Definition Language (IDL) statements.</span></span>  
  
### <a name="platform-invoke-examples"></a><span data-ttu-id="b1bf0-142">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="b1bf0-142">Platform Invoke Examples</span></span>  
 <span data-ttu-id="b1bf0-143">Примеры вызовов неуправляемого кода в этом разделе иллюстрируют использование атрибута `RegistryPermission` с модификаторами обхода стека.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-143">The platform invoke samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="b1bf0-144">В примере кода ниже модификаторы <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny` и `PermitOnly` не учитываются.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-144">In the following code example, the <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny`, and `PermitOnly` modifiers are ignored.</span></span>  
  
```  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionAssert();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="b1bf0-145">Однако модификатор `Demand` в следующем примере принимается.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-145">However, the `Demand` modifier in the following example is accepted.</span></span>  
  
```  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="b1bf0-146">Модификаторы <xref:System.Security.Permissions.SecurityAction> действительно правильно работают, если они заданы для класса, содержащего (инкапсулирующего) вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-146"><xref:System.Security.Permissions.SecurityAction> modifiers do work correctly if they are placed on a class that contains (wraps) the platform invoke call.</span></span>  
  
```cpp  
      [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
public ref class PInvokeWrapper  
{  
public:  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
};  
```  
  
```csharp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
class PInvokeWrapper  
{  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
}  
```  
  
 <span data-ttu-id="b1bf0-147">Модификаторы <xref:System.Security.Permissions.SecurityAction> также правильно работают в сценарии с вложением, когда они задаются для объекта, выполняющего вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-147"><xref:System.Security.Permissions.SecurityAction> modifiers also work correctly in a nested scenario where they are placed on the caller of the platform invoke call:</span></span>  
  
```cpp  
      {  
public ref class PInvokeWrapper  
public:  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
  
    [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
};  
```  
  
```csharp  
class PInvokeScenario  
{  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionInternal();  
  
    [RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
}  
```  
  
#### <a name="com-interop-examples"></a><span data-ttu-id="b1bf0-148">Примеры COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b1bf0-148">COM Interop Examples</span></span>  
 <span data-ttu-id="b1bf0-149">Примеры COM-взаимодействия в этом разделе иллюстрируют использование атрибута `RegistryPermission` с модификаторами обхода стека.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-149">The COM interop samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="b1bf0-150">В приведенных ниже объявлениях интерфейса COM-взаимодействия модификаторы `Assert`, `Deny` и `PermitOnly` не учитываются по аналогии с примерами вызовов неуправляемого кода в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-150">The following COM interop interface declarations ignore the `Assert`, `Deny`, and `PermitOnly` modifiers, similarly to the platform invoke examples in the previous section.</span></span>  
  
```  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDenyStubsItf  
{  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
 <span data-ttu-id="b1bf0-151">Кроме того, модификатор `Demand` недопустим в сценариях объявления интерфейса COM-взаимодействия, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b1bf0-151">Additionally, the `Demand` modifier is not accepted in COM interop interface declaration scenarios, as shown in the following example.</span></span>  
  
```  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDemandStubsItf  
{  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1bf0-152">См. также</span><span class="sxs-lookup"><span data-stu-id="b1bf0-152">See Also</span></span>  
 [<span data-ttu-id="b1bf0-153">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="b1bf0-153">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="b1bf0-154">Задание точки входа</span><span class="sxs-lookup"><span data-stu-id="b1bf0-154">Specifying an Entry Point</span></span>](../../../docs/framework/interop/specifying-an-entry-point.md)  
 [<span data-ttu-id="b1bf0-155">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="b1bf0-155">Specifying a Character Set</span></span>](../../../docs/framework/interop/specifying-a-character-set.md)  
 [<span data-ttu-id="b1bf0-156">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="b1bf0-156">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="b1bf0-157">Вопросы безопасности при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="b1bf0-157">Platform Invoke Security Considerations</span></span>](http://msdn.microsoft.com/en-us/bbcc67f7-50b5-4917-88ed-cb15470409fb)  
 [<span data-ttu-id="b1bf0-158">Идентификация функций в библиотеках DLL</span><span class="sxs-lookup"><span data-stu-id="b1bf0-158">Identifying Functions in DLLs</span></span>](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [<span data-ttu-id="b1bf0-159">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="b1bf0-159">Creating a Class to Hold DLL Functions</span></span>](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)  
 [<span data-ttu-id="b1bf0-160">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="b1bf0-160">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
