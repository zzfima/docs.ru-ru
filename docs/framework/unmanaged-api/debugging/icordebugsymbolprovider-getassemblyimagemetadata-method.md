---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 3ee80c18d3091406bf0bbd5b22c5f6021888906d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791656"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="0a7dc-102">Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="0a7dc-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="0a7dc-103">Возвращает метаданные из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="0a7dc-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a7dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a7dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a7dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a7dc-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="0a7dc-106">заполняет Указатель на адрес объекта [икордебугмеморибуффер](icordebugmemorybuffer-interface.md) , который содержит сведения о размере и адресе метаданных объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="0a7dc-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a7dc-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="0a7dc-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a7dc-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0a7dc-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a7dc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0a7dc-109">Requirements</span></span>  
 <span data-ttu-id="0a7dc-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a7dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a7dc-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a7dc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a7dc-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a7dc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a7dc-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a7dc-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7dc-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a7dc-114">See also</span></span>

- [<span data-ttu-id="0a7dc-115">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="0a7dc-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="0a7dc-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0a7dc-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
