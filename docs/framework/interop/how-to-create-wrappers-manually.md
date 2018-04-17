---
title: Практическое руководство. Создание оболочек вручную
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f610a3e1ed6ba554818945d651c00508e0c87cc
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-wrappers-manually"></a>Практическое руководство. Создание оболочек вручную
Если вы решили объявлять типы COM в управляемом исходном коде вручную, лучше всего начать с существующего файла языка IDL или библиотеки типов. Если у вас нет файла IDL или вы не можете создать файл библиотеки типов, можно имитировать типы COM, создав управляемые объявления и экспортировав получившуюся сборку в библиотеку типов.  
  
### <a name="to-simulate-com-types-from-managed-source"></a>Имитация типов COM из управляемого источника  
  
1.  Объявите типы на языке, совместимом со спецификацией CLS, и скомпилируйте файл.  
  
2.  Экспортируйте сборку, содержащую типы, с помощью [программы экспорта библиотек типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).  
  
3.  Экспортированная библиотека типов COM используется в качестве основы для объявления управляемых типов, ориентированных на COM.  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a>Создание вызываемой оболочки времени выполнения  
  
1.  Если у вас есть IDL-файл или файл библиотеки типов, решите, какие классы и интерфейсы нужно включить в пользовательскую вызываемую оболочку времени выполнения. Вы можете исключить любые типы, которые не будут использоваться в приложении прямо или косвенно.  
  
2.  Создайте файл исходного кода на языке, совместимом с CLS, и объявите типы. Полное описание процедуры преобразования при импорте см. в разделе [Обзор преобразования библиотеки типов в сборку](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100)). Фактически при создании пользовательской вызываемой оболочки времени выполнения вы вручную выполняете все операции по преобразованию типов, предоставляемые [программой импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md). В примере в следующем разделе показаны типы в файле IDL или файле библиотеки типов и соответствующие типы в коде C#.  
  
3.  После завершения объявлений следует выполнить компиляцию этого файла так же, как и компиляцию любого другого управляемого исходного кода.  
  
4.  Как и в случае с типами, импортированными с помощью программы Tlbimp.exe, для некоторых типов требуются дополнительные сведения, которые можно добавить непосредственно в код. Подробнее об этом см. в разделе [Практическое руководство. Редактирование сборок взаимодействия](https://msdn.microsoft.com/library/16aacb20-2269-42bf-a812-b6a7df17e277(v=vs.100)).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример кода интерфейса `ISATest` и класса `SATest` в IDL вместе с соответствующими типами в исходном коде C#.  
  
 **Файл IDL или файл библиотеки типов**  
  
```  
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
  
 **Оболочка в управляемом исходном коде**  
  
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
  
## <a name="see-also"></a>См. также  
 [Настройка вызываемых оболочек времени выполнения](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100))  
 [Типы данных COM](https://msdn.microsoft.com/library/f93ae35d-a416-4218-8700-c8218cc90061(v=vs.100))  
 [Как: редактирование сборок взаимодействия](https://msdn.microsoft.com/library/16aacb20-2269-42bf-a812-b6a7df17e277(v=vs.100))  
 [Общие сведения о преобразовании библиотеки типов в сборку](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100))  
 [Tlbimp.exe (программа экспорта библиотек типов)](../tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (программа экспорта библиотек типов)](../tools/tlbexp-exe-type-library-exporter.md)
