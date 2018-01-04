---
title: "Атрибут GUID_ManagedName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GUID_ManagedName
api_location: alink.dll
api_type: COM
f1_keywords: GUID_ManagedName
helpviewer_keywords: GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 116a9e38b9885f0d0a5afc8f4915b9ce2b50f1dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="077d4-102">Атрибут GUID_ManagedName</span><span class="sxs-lookup"><span data-stu-id="077d4-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="077d4-103">Определяет настраиваемый атрибут интерфейса, указывающее имя управляемого пространства имен для библиотеки COM-модели объектов компонента.</span><span class="sxs-lookup"><span data-stu-id="077d4-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="077d4-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="077d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="077d4-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="077d4-106">Имя управляемого пространства имен для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="077d4-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="077d4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="077d4-107">Definition</span></span>  
 <span data-ttu-id="077d4-108">`GUID_ManagedName`определяется в Cor.h следующим образом:</span><span class="sxs-lookup"><span data-stu-id="077d4-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="077d4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="077d4-109">Remarks</span></span>  
 <span data-ttu-id="077d4-110">Настраиваемый атрибут интерфейса определяет метаданные для объекта в библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="077d4-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="077d4-111">Используйте <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> или <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> получить имя управляемого из атрибута.</span><span class="sxs-lookup"><span data-stu-id="077d4-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="077d4-112">Дополнительные сведения см. в разделе [атрибуты интерфейса](/cpp/windows/interface-attributes) в Visual C++ справочной документации.</span><span class="sxs-lookup"><span data-stu-id="077d4-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="077d4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="077d4-113">Example</span></span>  
 <span data-ttu-id="077d4-114">В следующем примере показано определение библиотеки с помощью `GUID_ManagedName` атрибута.</span><span class="sxs-lookup"><span data-stu-id="077d4-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="077d4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="077d4-115">Requirements</span></span>  
 <span data-ttu-id="077d4-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="077d4-116">**Header:** Cor.h</span></span>
