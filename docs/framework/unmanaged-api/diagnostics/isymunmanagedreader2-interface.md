---
title: Интерфейс ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 890053e1bf2e0648a41cca718e94edcf21c7e612
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165988"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="879ec-102">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="879ec-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="879ec-103">Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="879ec-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="879ec-104">Этот интерфейс расширяет [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="879ec-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="879ec-105">Методы</span><span class="sxs-lookup"><span data-stu-id="879ec-105">Methods</span></span>  
  
|<span data-ttu-id="879ec-106">Метод</span><span class="sxs-lookup"><span data-stu-id="879ec-106">Method</span></span>|<span data-ttu-id="879ec-107">Описание</span><span class="sxs-lookup"><span data-stu-id="879ec-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="879ec-108">Метод GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="879ec-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="879ec-109">Получение метода средства чтения символов, получив токен метода и номеру версии, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="879ec-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="879ec-110">Метод GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="879ec-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="879ec-111">Возвращает каждый метод, который содержит сведения о строке в указанный документ.</span><span class="sxs-lookup"><span data-stu-id="879ec-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="879ec-112">Метод GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="879ec-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="879ec-113">Получает настраиваемый атрибут, в зависимости от его имени.</span><span class="sxs-lookup"><span data-stu-id="879ec-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="879ec-114">Требования</span><span class="sxs-lookup"><span data-stu-id="879ec-114">Requirements</span></span>  
 <span data-ttu-id="879ec-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="879ec-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879ec-116">См. также</span><span class="sxs-lookup"><span data-stu-id="879ec-116">See also</span></span>

- [<span data-ttu-id="879ec-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="879ec-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="879ec-118">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="879ec-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
