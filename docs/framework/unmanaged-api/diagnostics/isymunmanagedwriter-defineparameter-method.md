---
title: Метод ISymUnmanagedWriter::DefineParameter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5b82415635980f5bd4e13e87a0a03ec5b7032bb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777322"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="fe194-102">Метод ISymUnmanagedWriter::DefineParameter</span><span class="sxs-lookup"><span data-stu-id="fe194-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="fe194-103">Определяет один параметр в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="fe194-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="fe194-104">Тип параметра берутся из (последовательность) позиция параметра в подписи метода.</span><span class="sxs-lookup"><span data-stu-id="fe194-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="fe194-105">Если параметры определены в метаданных для данного метода, у вас нет определять их с помощью этого метода.</span><span class="sxs-lookup"><span data-stu-id="fe194-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="fe194-106">Средства чтения символов необходимо проверить обычные метаданные для параметров перед проверкой в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="fe194-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe194-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe194-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe194-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe194-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fe194-109">[in] Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="fe194-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="fe194-110">[in] Атрибуты параметра.</span><span class="sxs-lookup"><span data-stu-id="fe194-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="fe194-111">[in] Подпись параметра.</span><span class="sxs-lookup"><span data-stu-id="fe194-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="fe194-112">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="fe194-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="fe194-113">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="fe194-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="fe194-114">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="fe194-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="fe194-115">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="fe194-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe194-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe194-116">Return Value</span></span>  
 <span data-ttu-id="fe194-117">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fe194-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe194-118">Требования</span><span class="sxs-lookup"><span data-stu-id="fe194-118">Requirements</span></span>  
 <span data-ttu-id="fe194-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fe194-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe194-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fe194-120">See also</span></span>

- [<span data-ttu-id="fe194-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="fe194-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
