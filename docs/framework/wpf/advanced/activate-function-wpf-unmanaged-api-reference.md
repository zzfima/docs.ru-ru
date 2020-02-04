---
title: Активация функции — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734511"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Функция Activate (Справочник по неуправляемым ИНТЕРФЕЙСам WPF)

Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.

Используется инфраструктурой Windows Presentation Foundation (WPF) для управления Windows.

## <a name="syntax"></a>Синтаксис

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Параметры

`pParameters`\
Указатель на параметры активации окна.

`ppInner`\
Указатель на адрес буфера с одним элементом, который содержит указатель на объект <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>.

## <a name="requirements"></a>Требования

**Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).

**КОМПОНОВКИ**

В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll

В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll

**Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>См. также раздел

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
