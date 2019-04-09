---
title: Метод ICorDebugSymbolProvider::GetMethodProps
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784fcb10e9c0c3c6ff50c25d47bb4fb3fd5762ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161113"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="4d5dc-102">Метод ICorDebugSymbolProvider::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="4d5dc-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="4d5dc-103">Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d5dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d5dc-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d5dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d5dc-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="4d5dc-106">[in] Относительный виртуальный адрес в методе, сведения о котором требуется извлечь.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="4d5dc-107">[out] Указатель на токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="4d5dc-108">[out] Указатель на количество универсальных параметров, связанных с данным методом.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="4d5dc-109">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="4d5dc-110">См. раздел примeчаний.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="4d5dc-111">[out] Указатель на размер возвращаемого массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="4d5dc-112">[out] Буфер, в котором хранятся сигнатуры TypeSpec для всех универсальных параметров.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d5dc-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d5dc-113">Remarks</span></span>  
 <span data-ttu-id="4d5dc-114">Чтобы получить требуемый размер метода `signature` массива, задайте `cbSignature` аргумент 0 и `signature` для **null**.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="4d5dc-115">После возврата метода параметр `pcbSignature` будет содержать число байт, требуемое для массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d5dc-116">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4d5dc-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d5dc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4d5dc-117">Requirements</span></span>  
 <span data-ttu-id="4d5dc-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d5dc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d5dc-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d5dc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d5dc-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d5dc-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4d5dc-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4d5dc-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d5dc-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4d5dc-122">See also</span></span>

- [<span data-ttu-id="4d5dc-123">Метод GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="4d5dc-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="4d5dc-124">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4d5dc-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4d5dc-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4d5dc-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
