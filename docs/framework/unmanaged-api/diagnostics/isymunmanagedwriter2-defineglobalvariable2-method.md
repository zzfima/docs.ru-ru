---
title: Метод ISymUnmanagedWriter2::DefineGlobalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: 12475b1ac8a1a81e565aa689eac2ae1a9b55e73a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438283"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="62532-102">Метод ISymUnmanagedWriter2::DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="62532-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="62532-103">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="62532-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62532-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62532-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62532-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62532-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="62532-106">окне Имя глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="62532-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="62532-107">окне Атрибуты глобальных переменных.</span><span class="sxs-lookup"><span data-stu-id="62532-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="62532-108">окне Маркер метаданных сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="62532-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="62532-109">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="62532-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="62532-110">окне Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="62532-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="62532-111">окне Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="62532-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="62532-112">окне Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="62532-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62532-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="62532-113">Return Value</span></span>  
 <span data-ttu-id="62532-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="62532-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62532-115">Требования</span><span class="sxs-lookup"><span data-stu-id="62532-115">Requirements</span></span>  
 <span data-ttu-id="62532-116">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="62532-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62532-117">См. также</span><span class="sxs-lookup"><span data-stu-id="62532-117">See also</span></span>

- [<span data-ttu-id="62532-118">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="62532-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="62532-119">Метод DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="62532-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
