---
title: "Метод ICorDebugType::GetRank"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetRank
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eb27cc774ccd199151059049bbcc9c4e17a4de59
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="b165b-102">Метод ICorDebugType::GetRank</span><span class="sxs-lookup"><span data-stu-id="b165b-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="b165b-103">Возвращает число измерений в тип массива.</span><span class="sxs-lookup"><span data-stu-id="b165b-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b165b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b165b-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b165b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b165b-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="b165b-106">[out] Указатель на число измерений.</span><span class="sxs-lookup"><span data-stu-id="b165b-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b165b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b165b-107">Requirements</span></span>  
 <span data-ttu-id="b165b-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b165b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b165b-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b165b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b165b-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b165b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b165b-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b165b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
