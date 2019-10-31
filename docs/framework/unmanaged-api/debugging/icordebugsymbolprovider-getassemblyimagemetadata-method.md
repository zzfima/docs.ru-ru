---
title: 'Метод метод icordebugsymbolprovider:: GetAssemblyImageMetadata'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: fb08df3b594e0c34dfe4ca791983b0c111239b23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138904"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="a1495-102">Метод метод icordebugsymbolprovider:: GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="a1495-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="a1495-103">Возвращает метаданные из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="a1495-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1495-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1495-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1495-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1495-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="a1495-106">заполняет Указатель на адрес объекта [икордебугмеморибуффер](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) , который содержит сведения о размере и адресе метаданных объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="a1495-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1495-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a1495-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1495-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a1495-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1495-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a1495-109">Requirements</span></span>  
 <span data-ttu-id="a1495-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1495-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1495-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1495-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1495-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1495-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1495-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1495-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1495-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a1495-114">See also</span></span>

- [<span data-ttu-id="a1495-115">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a1495-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a1495-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a1495-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
