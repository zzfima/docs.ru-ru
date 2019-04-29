---
title: Метод ICorDebugAssembly::GetCodeBase
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetCodeBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetCodeBase
helpviewer_keywords:
- GetCodeBase method [.NET Framework debugging]
- ICorDebugAssembly::GetCodeBase method [.NET Framework debugging]
ms.assetid: 48adc154-9058-4fef-9c43-e9aad80e4dbf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6236d6b5349a9c2a528a85559c0cbc02c8da381
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645491"
---
# <a name="icordebugassemblygetcodebase-method"></a><span data-ttu-id="87c8a-102">Метод ICorDebugAssembly::GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="87c8a-102">ICorDebugAssembly::GetCodeBase Method</span></span>
<span data-ttu-id="87c8a-103">Этот метод не реализован в текущей версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87c8a-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87c8a-104">Syntax</span></span>  
  
```  
HRESULT GetCodeBase (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR szName[]  
);  
```
