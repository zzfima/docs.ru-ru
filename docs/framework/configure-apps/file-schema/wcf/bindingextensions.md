---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: 34ba198de33ae4aa1882d13f74bd2d538999a0c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919791"
---
# <a name="bindingextensions"></a><span data-ttu-id="ddda6-101">\<Биндинжекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="ddda6-101">\<bindingExtensions></span></span>
<span data-ttu-id="ddda6-102">В этом разделе описывается использование пользовательской привязки из файла конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="ddda6-102">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="ddda6-103">Добавить пользовательскую привязку в эту коллекцию можно с помощью ключевого слова `add`, установив атрибут `type` элемента равным пользовательской привязке, а атрибут `name` равным имени пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ddda6-103">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="ddda6-104">Расширения привязки позволяют пользователю создавать привязки для использования в составе конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ddda6-104">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="ddda6-105">Ну уровне программирования расширение привязки представляет собой тип, реализующий абстрактный класс <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="ddda6-105">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="ddda6-106">В следующем примере элемент `add` и атрибут `name` используются для добавления расширения привязки в раздел `bindingElementExtensions` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ddda6-106">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="ddda6-107">Чтобы добавить в элемент возможность настройки, пользователю следует записать и зарегистрировать элемент `bindingSection`.</span><span class="sxs-lookup"><span data-stu-id="ddda6-107">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="ddda6-108">Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="ddda6-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="ddda6-109">После определения элемента и его типа конфигурации расширение может быть использовано конечной точкой, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ddda6-109">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="ddda6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ddda6-110">See also</span></span>

- [<span data-ttu-id="ddda6-111">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="ddda6-111">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
