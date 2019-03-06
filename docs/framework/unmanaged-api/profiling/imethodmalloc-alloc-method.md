---
title: Метод IMethodMalloc::Alloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351259"
---
# <a name="imethodmallocalloc-method"></a>Метод IMethodMalloc::Alloc

Пытается выделить указанный объем памяти для нового тела функции промежуточного языка MSIL.

## <a name="syntax"></a>Синтаксис

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Параметры

`cb`\
[in] Число байтов, выделенных для тела метода.

## <a name="remarks"></a>Примечания

 Выделенная память начинается по адресу больше, чем базовый адрес модуля, связанного с данным распределителем. Другими словами каждый распределитель создается для определенного модуля и предпринимает попытку выделения памяти с положительным смещением от базового адреса. Если `Alloc` не удается выделить запрошенное число байт по адресу больше, чем базовый адрес модуля, он возвращает значение E_OUTOFMEMORY, независимо от фактического объема доступной памяти.

 `Alloc` Метод должен использоваться в сочетании с [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) метод.

## <a name="requirements"></a>Требования
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** CorProf.idl, CorProf.h

 **Библиотека:** CorGuids.lib

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс IMethodMalloc](imethodmalloc-interface.md)