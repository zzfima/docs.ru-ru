---
title: Глобальные статические функции отладки
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
ms.openlocfilehash: c20d8719b63cb40074dc740506ae4a3c0fc3a251
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793783"
---
# <a name="debugging-global-static-functions"></a><span data-ttu-id="a371a-102">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="a371a-102">Debugging Global Static Functions</span></span>
<span data-ttu-id="a371a-103">В этом разделе описываются неуправляемые глобальные статистические функции, которые используют API отладки.</span><span class="sxs-lookup"><span data-stu-id="a371a-103">This section describes the unmanaged global static functions that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a371a-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a371a-104">In This Section</span></span>  
 [<span data-ttu-id="a371a-105">Функция _EFN_GetManagedExcepStack</span><span class="sxs-lookup"><span data-stu-id="a371a-105">_EFN_GetManagedExcepStack Function</span></span>](efn-getmanagedexcepstack-function.md)  
 <span data-ttu-id="a371a-106">Учитывая адрес объекта управляемого исключения, возвращает строковую версию трассировки стека, содержащейся внутри.</span><span class="sxs-lookup"><span data-stu-id="a371a-106">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
 [<span data-ttu-id="a371a-107">Функция _EFN_GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="a371a-107">_EFN_GetManagedObjectFieldInfo Function</span></span>](efn-getmanagedobjectfieldinfo-function.md)  
 <span data-ttu-id="a371a-108">Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.</span><span class="sxs-lookup"><span data-stu-id="a371a-108">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
 [<span data-ttu-id="a371a-109">Функция _EFN_GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="a371a-109">_EFN_GetManagedObjectName Function</span></span>](efn-getmanagedobjectname-function.md)  
 <span data-ttu-id="a371a-110">Получает имя типа с помощью предоставленного указателя управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="a371a-110">Gets the name of a type by using the provided managed object pointer.</span></span>  
  
 [<span data-ttu-id="a371a-111">Функция _EFN_StackTrace</span><span class="sxs-lookup"><span data-stu-id="a371a-111">_EFN_StackTrace Function</span></span>](efn-stacktrace-function.md)  
 <span data-ttu-id="a371a-112">Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="a371a-112">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
 [<span data-ttu-id="a371a-113">Функция CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="a371a-113">CLRDataCreateInstance Function</span></span>](clrdatacreateinstance-function.md)  
 <span data-ttu-id="a371a-114">Вызывается службами доступа к данным среды CLR для создания указанного объекта интерфейса для заданного целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="a371a-114">Called by the common language runtime (CLR) data access services to create the specified interface object for the specified target process.</span></span>  
  
 [<span data-ttu-id="a371a-115">Указатель функции PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="a371a-115">PFN_CLRDataCreateInstance Function Pointer</span></span>](pfn-clrdatacreateinstance-function-pointer.md)  
 <span data-ttu-id="a371a-116">Указывает на функцию, вызываемую службами доступа к данным среды CLR, чтобы создать указанный объект интерфейса для заданного целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="a371a-116">Points to a function that is called by the CLR data access services to create the specified interface object for the specified target process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a371a-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a371a-117">Related Sections</span></span>  
 [<span data-ttu-id="a371a-118">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="a371a-118">Debugging Coclasses</span></span>](debugging-coclasses.md)  
  
 [<span data-ttu-id="a371a-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a371a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)  
  
 [<span data-ttu-id="a371a-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="a371a-120">Debugging Enumerations</span></span>](debugging-enumerations.md)  
  
 [<span data-ttu-id="a371a-121">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="a371a-121">Debugging Structures</span></span>](debugging-structures.md)
