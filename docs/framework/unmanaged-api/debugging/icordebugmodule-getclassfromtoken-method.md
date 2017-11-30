---
title: "Метод ICorDebugModule::GetClassFromToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetClassFromToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bd483eebc66b1274c0d28c46b3ccb1b1272f74b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="d71fe-102">Метод ICorDebugModule::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="d71fe-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="d71fe-103">Возвращает класс, указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="d71fe-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d71fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d71fe-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d71fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d71fe-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="d71fe-106">[in] `mdTypeDef` Токен метаданных, который ссылается на метаданные класса.</span><span class="sxs-lookup"><span data-stu-id="d71fe-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="d71fe-107">[out] Указатель на адрес объекта ICorDebugClass, который представляет класс.</span><span class="sxs-lookup"><span data-stu-id="d71fe-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d71fe-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d71fe-108">Requirements</span></span>  
 <span data-ttu-id="d71fe-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d71fe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d71fe-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d71fe-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d71fe-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d71fe-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d71fe-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d71fe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
