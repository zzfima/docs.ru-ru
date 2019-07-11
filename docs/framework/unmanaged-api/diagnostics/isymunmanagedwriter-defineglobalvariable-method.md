---
title: Метод ISymUnmanagedWriter::DefineGlobalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bc14c36563badb73ac9f9d955ea0c00f5330b4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777360"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="589cd-102">Метод ISymUnmanagedWriter::DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="589cd-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="589cd-103">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="589cd-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="589cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="589cd-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="589cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="589cd-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="589cd-106">[in] Указатель на `WCHAR` , определяющий имя глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="589cd-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="589cd-107">[in] Атрибутов глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="589cd-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="589cd-108">[in] Объект `ULONG32` указывает размер, в символах, из `signature` буфера.</span><span class="sxs-lookup"><span data-stu-id="589cd-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="589cd-109">[in] Подпись глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="589cd-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="589cd-110">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="589cd-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="589cd-111">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="589cd-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="589cd-112">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="589cd-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="589cd-113">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="589cd-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="589cd-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="589cd-114">Return Value</span></span>  
 <span data-ttu-id="589cd-115">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="589cd-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="589cd-116">Требования</span><span class="sxs-lookup"><span data-stu-id="589cd-116">Requirements</span></span>  
 <span data-ttu-id="589cd-117">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="589cd-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589cd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="589cd-118">See also</span></span>

- [<span data-ttu-id="589cd-119">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="589cd-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="589cd-120">Метод DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="589cd-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="589cd-121">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="589cd-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
