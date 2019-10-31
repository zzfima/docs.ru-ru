---
title: 'Метод ICorDebugSymbolProvider2:: Жетженерикдиктионаринфо'
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: c9f7206cac54d64c28eb50d81fea00a6f3c494d4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133634"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="0e98f-102">Метод ICorDebugSymbolProvider2:: Жетженерикдиктионаринфо</span><span class="sxs-lookup"><span data-stu-id="0e98f-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>

<span data-ttu-id="0e98f-103">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="0e98f-103">Retrieves a generic dictionary map.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e98f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e98f-104">Syntax</span></span>

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="0e98f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e98f-105">Parameters</span></span>

`ppMemoryBuffer`\
<span data-ttu-id="0e98f-106">заполняет Указатель на адрес объекта [икордебугмеморибуффер](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) , содержащего универсальную карту словаря.</span><span class="sxs-lookup"><span data-stu-id="0e98f-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="0e98f-107">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="0e98f-107">See the Remarks section for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e98f-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="0e98f-108">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="0e98f-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0e98f-109">This method is available with .NET Native only.</span></span>

<span data-ttu-id="0e98f-110">Карта состоит из двух разделов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="0e98f-110">The map consists of two top-level sections:</span></span>

- <span data-ttu-id="0e98f-111">[Каталог](#Directory) , содержащий относительные виртуальные адреса (RVA) всех словарей, входящих в эту карту.</span><span class="sxs-lookup"><span data-stu-id="0e98f-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>

- <span data-ttu-id="0e98f-112">[Куча](#Heap) с согласованием байтов, которая содержит сведения о создании экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="0e98f-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="0e98f-113">Она запускается сразу после последней записи каталога.</span><span class="sxs-lookup"><span data-stu-id="0e98f-113">It starts immediately after the last directory entry.</span></span>

<a name="Directory"></a>

## <a name="the-directory"></a><span data-ttu-id="0e98f-114">Каталог</span><span class="sxs-lookup"><span data-stu-id="0e98f-114">The Directory</span></span>

<span data-ttu-id="0e98f-115">Каждая запись в каталоге ссылается на смещение в куче; то есть это смещение относительно начала кучи.</span><span class="sxs-lookup"><span data-stu-id="0e98f-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="0e98f-116">Значения отдельных записей, не обязательно должны быть уникальными; несколько записей каталога могут указывать на одно и то же смещение в куче.</span><span class="sxs-lookup"><span data-stu-id="0e98f-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>

<span data-ttu-id="0e98f-117">Часть каталога универсальной карты словаря имеет следующую структуру.</span><span class="sxs-lookup"><span data-stu-id="0e98f-117">The directory portion of the generic dictionary map has the following structure:</span></span>

- <span data-ttu-id="0e98f-118">Первые 4 байта содержит число записей словаря (т. е. число относительных виртуальных адресов в словаре).</span><span class="sxs-lookup"><span data-stu-id="0e98f-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="0e98f-119">Мы будем называть это значение *N*. Если задан высокий бит, записи сортируются по относительному виртуальному адресу в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="0e98f-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>

- <span data-ttu-id="0e98f-120">Далее следуют записи каталога *N* .</span><span class="sxs-lookup"><span data-stu-id="0e98f-120">The *N* directory entries follow.</span></span> <span data-ttu-id="0e98f-121">Каждая запись состоит из 8 байт в двух 4-байтовых сегментах.</span><span class="sxs-lookup"><span data-stu-id="0e98f-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>

  - <span data-ttu-id="0e98f-122">Байты с 0 по 3: RVA; относительный виртуальный адрес словаря.</span><span class="sxs-lookup"><span data-stu-id="0e98f-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>

  - <span data-ttu-id="0e98f-123">Байты с 4 по 7: смещение; смещение относительно начала кучи.</span><span class="sxs-lookup"><span data-stu-id="0e98f-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>

<a name="Heap"></a>

## <a name="the-heap"></a><span data-ttu-id="0e98f-124">Куча</span><span class="sxs-lookup"><span data-stu-id="0e98f-124">The Heap</span></span>

<span data-ttu-id="0e98f-125">Размер кучи может быть вычислен модулем чтения потока путем вычитания длины потока из размера каталога + 4.</span><span class="sxs-lookup"><span data-stu-id="0e98f-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="0e98f-126">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="0e98f-126">In other words:</span></span>

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

<span data-ttu-id="0e98f-127">где размер каталога равен `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="0e98f-127">where the directory size is `N * 8`.</span></span>

<span data-ttu-id="0e98f-128">Формат каждого элемента сведений о создании экземпляра в куче выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0e98f-128">The format for each instantiation information item on the heap is:</span></span>

- <span data-ttu-id="0e98f-129">Длина этого элемента сведений о создании экземпляра в байтах в сжатом формате ECMA метаданных.</span><span class="sxs-lookup"><span data-stu-id="0e98f-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="0e98f-130">Значение исключает эти сведения о длине.</span><span class="sxs-lookup"><span data-stu-id="0e98f-130">The value excludes this length information.</span></span>

- <span data-ttu-id="0e98f-131">Число универсальных типов создания экземпляров, или *T*, в сжатом формате метаданных ECMA.</span><span class="sxs-lookup"><span data-stu-id="0e98f-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>

- <span data-ttu-id="0e98f-132">Типы *T* , каждый из которых представлен в формате сигнатуры типа ECMA.</span><span class="sxs-lookup"><span data-stu-id="0e98f-132">*T* types, each represented in ECMA type signature format.</span></span>

<span data-ttu-id="0e98f-133">Включение длины для каждого элемента кучи позволяет простую сортировку раздела каталога без влияния на кучу.</span><span class="sxs-lookup"><span data-stu-id="0e98f-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e98f-134">Требования</span><span class="sxs-lookup"><span data-stu-id="0e98f-134">Requirements</span></span>

<span data-ttu-id="0e98f-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e98f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="0e98f-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e98f-136">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0e98f-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e98f-137">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0e98f-138">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e98f-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0e98f-139">См. также</span><span class="sxs-lookup"><span data-stu-id="0e98f-139">See also</span></span>

- [<span data-ttu-id="0e98f-140">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="0e98f-140">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="0e98f-141">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0e98f-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
