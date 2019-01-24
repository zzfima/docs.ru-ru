---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: aaf0dd9d6918f2c248942cee3773eee8332adda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552844"
---
# <a name="binding"></a>Привязка
wmi Binding  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс Binding не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс Binding имеет следующие свойства.  
  
### <a name="bindingelements"></a>BindingElements  
 Тип данных: Массив BindingElement  
  
 Тип доступа: Только чтение  
  
 Коллекция элементов привязки, реализованных привязкой.  
  
### <a name="closetimeout"></a>CloseTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Интервал времени, предусмотренный для завершения операции закрытия.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя привязки.  
  
### <a name="namespace"></a>Пространство имен  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Пространство имен XML привязки.  
  
### <a name="opentimeout"></a>OpenTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Интервал времени, предусмотренный для завершения операции открытия.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Интервал времени, предусмотренный для завершения операции получения.  
  
### <a name="scheme"></a>Схема  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Схема транспорта универсальных кодов ресурсов (URI), которая используется производствами каналов и прослушивателей, созданными привязкой.  
  
### <a name="sendtimeout"></a>SendTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Интервал времени, предусмотренный для завершения операции отправки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.Binding>
