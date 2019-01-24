---
title: Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 78031ed80fe83b736a351886457f9200534f470b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591517"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a>Параметры  
 pMsg  
 Указатель на сообщение.  
  
 appUnhandled  
 `true` Если приложение уже получил возможность для обработки входящего сообщения, но не предусмотрена. в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. в разделе [системные требования .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **БИБЛИОТЕКА DLL:**  
  
 В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll  
  
 В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Справочник по неуправляемым API WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
