---
title: Метод ICorDebugProcess2::GetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 2d5b07acb9dc374fdd8872ed982a92171da28603
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137231"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="c5250-102">Метод ICorDebugProcess2::GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c5250-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="c5250-103">Возвращает текущие параметры флага компилятора, используемые средой CLR для выбора правильного предварительно скомпилированного (то есть машинного) образа для загрузки в этот процесс.</span><span class="sxs-lookup"><span data-stu-id="c5250-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5250-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5250-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5250-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5250-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="c5250-106">заполняет Указатель на побитовую комбинацию значений перечисления [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) , которые используются для выбора правильного предварительно скомпилированного изображения для загрузки.</span><span class="sxs-lookup"><span data-stu-id="c5250-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5250-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="c5250-107">Remarks</span></span>  
 <span data-ttu-id="c5250-108">Используйте метод [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) , чтобы задать флаги, которые среда CLR будет использовать для выбора правильного предварительно скомпилированного изображения для загрузки.</span><span class="sxs-lookup"><span data-stu-id="c5250-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5250-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c5250-109">Requirements</span></span>  
 <span data-ttu-id="c5250-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5250-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5250-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5250-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5250-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5250-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5250-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5250-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
