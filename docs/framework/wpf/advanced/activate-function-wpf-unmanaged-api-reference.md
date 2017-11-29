---
title: "Активировать функции (WPF Справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: Acrivate
api_location: PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68f3f2a29da11a648b8c635667de6493a04ccd54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c7cf7-102">Активировать функции (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="c7cf7-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="c7cf7-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="c7cf7-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="c7cf7-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="c7cf7-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7cf7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7cf7-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7cf7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7cf7-106">Parameters</span></span>  
 <span data-ttu-id="c7cf7-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="c7cf7-107">pParameters</span></span>  
 <span data-ttu-id="c7cf7-108">Указатель на параметры активации окна.</span><span class="sxs-lookup"><span data-stu-id="c7cf7-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="c7cf7-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="c7cf7-109">ppInner</span></span>  
 <span data-ttu-id="c7cf7-110">Указатель на адрес буфера одиночный элемент, который содержит указатель на <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> объект.</span><span class="sxs-lookup"><span data-stu-id="c7cf7-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7cf7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c7cf7-111">Requirements</span></span>  
 <span data-ttu-id="c7cf7-112">**Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7cf7-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7cf7-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="c7cf7-113">**DLL:**</span></span>  
  
 <span data-ttu-id="c7cf7-114">В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="c7cf7-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="c7cf7-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="c7cf7-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="c7cf7-116">**Версия платформы .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7cf7-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7cf7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c7cf7-117">See Also</span></span>  
 [<span data-ttu-id="c7cf7-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="c7cf7-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
