---
title: '&lt;bindingExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: f99b38ede66dbecb44f9e8e67f921943071672ca
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750779"
---
# <a name="ltbindingextensionsgt"></a>&lt;bindingExtensions&gt;
В этом разделе описывается использование пользовательской привязки из файла конфигурации компьютера или приложения. Добавить пользовательскую привязку в эту коллекцию можно с помощью ключевого слова `add`, установив атрибут `type` элемента равным пользовательской привязке, а атрибут `name` равным имени пользовательской привязки.  
  
 Расширения привязки позволяют пользователю создавать привязки для использования в составе конфигурации конечной точки. Ну уровне программирования расширение привязки представляет собой тип, реализующий абстрактный класс <xref:System.ServiceModel.Channels.Binding>.  
  
 В следующем примере элемент `add` и атрибут `name` используются для добавления расширения привязки в раздел `bindingElementExtensions` файла конфигурации.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Чтобы добавить в элемент возможность настройки, пользователю следует записать и зарегистрировать элемент `bindingSection`. Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.  
  
 После определения элемента и его типа конфигурации расширение может быть использовано конечной точкой, как показано в следующем примере.  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a>См. также  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)
