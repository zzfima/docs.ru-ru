---
title: Практическое руководство. Создание оболочек вручную
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5db0ec9050c74b27d3ee25a99dcf8e2319835ffb
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894220"
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="a739d-102">Практическое руководство. Создание оболочек вручную</span><span class="sxs-lookup"><span data-stu-id="a739d-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="a739d-103">Если вы решили объявлять типы COM в управляемом исходном коде вручную, лучше всего начать с существующего файла языка IDL или библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="a739d-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="a739d-104">Если у вас нет файла IDL или вы не можете создать файл библиотеки типов, можно имитировать типы COM, создав управляемые объявления и экспортировав получившуюся сборку в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="a739d-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="a739d-105">Имитация типов COM из управляемого источника</span><span class="sxs-lookup"><span data-stu-id="a739d-105">To simulate COM types from managed source</span></span>  
  
1. <span data-ttu-id="a739d-106">Объявите типы на языке, совместимом со спецификацией CLS, и скомпилируйте файл.</span><span class="sxs-lookup"><span data-stu-id="a739d-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2. <span data-ttu-id="a739d-107">Экспортируйте сборку, содержащую типы, с помощью [программы экспорта библиотек типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="a739d-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3. <span data-ttu-id="a739d-108">Экспортированная библиотека типов COM используется в качестве основы для объявления управляемых типов, ориентированных на COM.</span><span class="sxs-lookup"><span data-stu-id="a739d-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="a739d-109">Создание вызываемой оболочки времени выполнения</span><span class="sxs-lookup"><span data-stu-id="a739d-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1. <span data-ttu-id="a739d-110">Если у вас есть IDL-файл или файл библиотеки типов, решите, какие классы и интерфейсы нужно включить в пользовательскую вызываемую оболочку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a739d-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="a739d-111">Вы можете исключить любые типы, которые не будут использоваться в приложении прямо или косвенно.</span><span class="sxs-lookup"><span data-stu-id="a739d-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2. <span data-ttu-id="a739d-112">Создайте файл исходного кода на языке, совместимом с CLS, и объявите типы.</span><span class="sxs-lookup"><span data-stu-id="a739d-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="a739d-113">Полное описание процедуры преобразования при импорте см. в разделе [Обзор преобразования библиотеки типов в сборку](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a739d-113">See [Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) for a complete description of the import conversion process.</span></span> <span data-ttu-id="a739d-114">Фактически при создании пользовательской вызываемой оболочки времени выполнения вы вручную выполняете все операции по преобразованию типов, предоставляемые [программой импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="a739d-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="a739d-115">В примере в следующем разделе показаны типы в файле IDL или файле библиотеки типов и соответствующие типы в коде C#.</span><span class="sxs-lookup"><span data-stu-id="a739d-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3. <span data-ttu-id="a739d-116">После завершения объявлений следует выполнить компиляцию этого файла так же, как и компиляцию любого другого управляемого исходного кода.</span><span class="sxs-lookup"><span data-stu-id="a739d-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4. <span data-ttu-id="a739d-117">Как и в случае с типами, импортированными с помощью программы Tlbimp.exe, для некоторых типов требуются дополнительные сведения, которые можно добавить непосредственно в код.</span><span class="sxs-lookup"><span data-stu-id="a739d-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="a739d-118">Подробную информацию см. в разделе [Практическое руководство. Изменение сборок взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a739d-118">For details, see [How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a739d-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a739d-119">Example</span></span>  
 <span data-ttu-id="a739d-120">Ниже приведен пример кода интерфейса `ISATest` и класса `SATest` в IDL вместе с соответствующими типами в исходном коде C#.</span><span class="sxs-lookup"><span data-stu-id="a739d-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="a739d-121">**Файл IDL или файл библиотеки типов**</span><span class="sxs-lookup"><span data-stu-id="a739d-121">**IDL or type library file**</span></span>  
  
```cpp
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="a739d-122">**Оболочка в управляемом исходном коде**</span><span class="sxs-lookup"><span data-stu-id="a739d-122">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a739d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a739d-123">See also</span></span>

- <span data-ttu-id="a739d-124">[Настройка вызываемых оболочек времени выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a739d-124">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>
- <span data-ttu-id="a739d-125">[Типы данных COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a739d-125">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>
- <span data-ttu-id="a739d-126">[Практическое руководство. Изменение сборок взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a739d-126">[How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span></span>
- <span data-ttu-id="a739d-127">[Общие сведения о преобразовании библиотеки типов в сборку](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a739d-127">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>
- [<span data-ttu-id="a739d-128">Tlbimp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="a739d-128">Tlbimp.exe (Type Library Importer)</span></span>](../tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="a739d-129">Tlbexp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="a739d-129">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
