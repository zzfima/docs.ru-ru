---
title: <add> из <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926711"
---
# <a name="add-of-defaultports"></a>\<Добавление > \<> дефаултпортс
Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<Усерекуессеадерсформетадатааддресс >  
\<Дефаултпортс >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|порт|Целочисленное значение, определяющее номер COM-порта по умолчанию.|  
|scheme|Строка, в которой указана группа параметров протокола, связанных с COM-портом.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Дефаултпортс >](defaultports.md)|Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
