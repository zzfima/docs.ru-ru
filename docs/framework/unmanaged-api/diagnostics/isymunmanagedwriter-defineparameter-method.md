---
title: "Метод ISymUnmanagedWriter::DefineParameter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineParameter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 166087a27d0aa7b100da563c25f7e5a52612ce50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="dcb1b-102">Метод ISymUnmanagedWriter::DefineParameter</span><span class="sxs-lookup"><span data-stu-id="dcb1b-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="dcb1b-103">Определяет отдельный параметр в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="dcb1b-104">Тип параметра берется из позицией параметра (последовательности) в сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="dcb1b-105">Если параметры определены в метаданных для данного метода, у вас определять их с помощью этого метода.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="dcb1b-106">Средства чтения символов необходимо проверить обычные метаданные для параметров перед проверкой хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcb1b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcb1b-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcb1b-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="dcb1b-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="dcb1b-109">[in] Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="dcb1b-110">[in] Атрибуты параметра.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="dcb1b-111">[in] Сигнатура параметра.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="dcb1b-112">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="dcb1b-113">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="dcb1b-114">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="dcb1b-115">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcb1b-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dcb1b-116">Return Value</span></span>  
 <span data-ttu-id="dcb1b-117">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="dcb1b-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb1b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="dcb1b-118">Requirements</span></span>  
 <span data-ttu-id="dcb1b-119">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dcb1b-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb1b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dcb1b-120">See Also</span></span>  
 [<span data-ttu-id="dcb1b-121">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dcb1b-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
