---
title: Интерфейс ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: f3305a7bb003fc50f772f1100f8a17d385e4d5fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449003"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="4bf49-102">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="4bf49-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="4bf49-103">Предоставляет функции для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="4bf49-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bf49-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4bf49-104">Methods</span></span>  
  
|<span data-ttu-id="4bf49-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4bf49-105">Method</span></span>|<span data-ttu-id="4bf49-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf49-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4bf49-107">Метод GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="4bf49-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="4bf49-108">Возвращает число локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="4bf49-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="4bf49-109">Метод GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="4bf49-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="4bf49-110">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="4bf49-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="4bf49-111">Метод InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="4bf49-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="4bf49-112">Позволяет вычислять границы методов перед первым вызовом метода [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4bf49-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="4bf49-113">Метод UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="4bf49-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="4bf49-114">Позволяет обновлять сведения о строке для метода, который не был перекомпилирован, но строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="4bf49-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="4bf49-115">Допускается использование разности для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="4bf49-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="4bf49-116">Метод UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="4bf49-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="4bf49-117">Позволяет компилятору опускать функции, которые не были изменены из потока базы данных программы (PDB) при условии, что сведения о строке соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="4bf49-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="4bf49-118">Правильная информация о строке может быть определена со старыми сведениями о строке PDB и одной разностью для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="4bf49-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4bf49-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4bf49-119">Requirements</span></span>  
 <span data-ttu-id="4bf49-120">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4bf49-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf49-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bf49-121">See also</span></span>

- [<span data-ttu-id="4bf49-122">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="4bf49-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
