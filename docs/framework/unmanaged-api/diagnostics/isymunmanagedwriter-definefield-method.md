---
title: Метод ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03c0a9d7315f5158948701d4322887104f0844c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603668"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="ee866-102">Метод ISymUnmanagedWriter::DefineField</span><span class="sxs-lookup"><span data-stu-id="ee866-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="ee866-103">Определяет одну переменную, не внутри метода.</span><span class="sxs-lookup"><span data-stu-id="ee866-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="ee866-104">Этот метод является, используемых для некоторых полей в классах, битовые поля и т. д.</span><span class="sxs-lookup"><span data-stu-id="ee866-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee866-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee866-105">Syntax</span></span>  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee866-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee866-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="ee866-107">[in] Метаданные типа или метода токена.</span><span class="sxs-lookup"><span data-stu-id="ee866-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="ee866-108">[in] Имя поля.</span><span class="sxs-lookup"><span data-stu-id="ee866-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ee866-109">[in] Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="ee866-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="ee866-110">[in] Объект `ULONG32` то есть размер в символах, буфера, требуемого для хранения подпись поля.</span><span class="sxs-lookup"><span data-stu-id="ee866-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="ee866-111">[in] Массив полей подписи.</span><span class="sxs-lookup"><span data-stu-id="ee866-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ee866-112">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="ee866-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ee866-113">[in] Первый адрес для спецификации поля.</span><span class="sxs-lookup"><span data-stu-id="ee866-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ee866-114">[in] Второй адрес для спецификации поля.</span><span class="sxs-lookup"><span data-stu-id="ee866-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ee866-115">[in] Третий адрес для спецификации поля.</span><span class="sxs-lookup"><span data-stu-id="ee866-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee866-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee866-116">Return Value</span></span>  
 <span data-ttu-id="ee866-117">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ee866-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee866-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ee866-118">Requirements</span></span>  
 <span data-ttu-id="ee866-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee866-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee866-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ee866-120">See also</span></span>
- [<span data-ttu-id="ee866-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ee866-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
