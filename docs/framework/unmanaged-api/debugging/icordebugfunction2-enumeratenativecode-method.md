---
title: Метод ICorDebugFunction2::EnumerateNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411792"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="e7ec9-102">Метод ICorDebugFunction2::EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="e7ec9-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="e7ec9-103">Получает указатель интерфейса на объект ICorDebugCodeEnum, содержащий инструкции машинного кода в функцию, который ссылается данный объект ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="e7ec9-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7ec9-104">`EnumerateNativeCode` не реализован в текущей версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7ec9-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ec9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7ec9-105">Syntax</span></span>  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e7ec9-106">Требования</span><span class="sxs-lookup"><span data-stu-id="e7ec9-106">Requirements</span></span>  
 <span data-ttu-id="e7ec9-107">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7ec9-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
