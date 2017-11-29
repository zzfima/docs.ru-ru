---
title: "Интерфейс ISymUnmanagedENCUpdate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate
helpviewer_keywords: ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 36ac53094751cb43ef122d439c7a784070c28182
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="9c221-102">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="9c221-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="9c221-103">Предоставляет функции для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="9c221-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c221-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9c221-104">Methods</span></span>  
  
|<span data-ttu-id="9c221-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9c221-105">Method</span></span>|<span data-ttu-id="9c221-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9c221-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c221-107">Метод GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="9c221-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="9c221-108">Возвращает количество локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="9c221-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="9c221-109">Метод GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="9c221-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="9c221-110">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="9c221-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="9c221-111">Метод InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="9c221-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="9c221-112">Метод границы должны быть вычислены до первого вызова позволяет [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9c221-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="9c221-113">Метод UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="9c221-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="9c221-114">Позволяет обновить строки для метода, который не был повторно скомпилирован, но его строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="9c221-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="9c221-115">Допускается разницы для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="9c221-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="9c221-116">Метод UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="9c221-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="9c221-117">Позволяет компилятору пропускать функции, которые не были изменены из потока программы базы данных (PDB), при условии, что сведения о строке соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="9c221-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="9c221-118">Правильные сведения строки можно определить с помощью старых сведений строки PDB и одного разностного для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="9c221-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c221-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9c221-119">Requirements</span></span>  
 <span data-ttu-id="9c221-120">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9c221-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c221-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9c221-121">See Also</span></span>  
 [<span data-ttu-id="9c221-122">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="9c221-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
