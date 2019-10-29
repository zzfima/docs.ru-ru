---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: bd6aeb32e0994bceb9e56bcb1c6267f4cb64a5a4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039143"
---
# <a name="bindingextensions"></a><span data-ttu-id="b9569-101">\<Биндинжекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="b9569-101">\<bindingExtensions></span></span>

<span data-ttu-id="b9569-102">В этом разделе описывается использование пользовательской привязки из файла конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="b9569-102">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="b9569-103">Добавить пользовательскую привязку в эту коллекцию можно с помощью ключевого слова `add`, установив атрибут `type` элемента равным пользовательской привязке, а атрибут `name` равным имени пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b9569-103">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>

<span data-ttu-id="b9569-104">Расширения привязки позволяют пользователю создавать привязки для использования в составе конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b9569-104">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="b9569-105">Ну уровне программирования расширение привязки представляет собой тип, реализующий абстрактный класс <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="b9569-105">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>

<span data-ttu-id="b9569-106">В следующем примере используется элемент `add`, а также атрибут `name` для добавления расширения привязки в раздел `bindingExtensions` файла конфигурации:</span><span class="sxs-lookup"><span data-stu-id="b9569-106">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingExtensions` section of the configuration file:</span></span>

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

<span data-ttu-id="b9569-107">Чтобы добавить в элемент возможность настройки, пользователю следует записать и зарегистрировать элемент `bindingSection`.</span><span class="sxs-lookup"><span data-stu-id="b9569-107">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="b9569-108">Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="b9569-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>

<span data-ttu-id="b9569-109">После определения элемента и его типа конфигурации расширение можно использовать как часть конечной точки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b9569-109">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example:</span></span>

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a><span data-ttu-id="b9569-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b9569-110">See also</span></span>

- [<span data-ttu-id="b9569-111">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b9569-111">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
