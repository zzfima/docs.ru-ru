---
title: '&lt;bindingElementExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: a93474a4f86fac2a6b211652e3ddc86901cf197f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747753"
---
# <a name="ltbindingelementextensionsgt"></a><span data-ttu-id="8b452-102">&lt;bindingElementExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="8b452-102">&lt;bindingElementExtensions&gt;</span></span>
<span data-ttu-id="8b452-103">В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="8b452-103">This section enables the use of a custom binding element from a machine or application configuration file.</span></span> <span data-ttu-id="8b452-104">Элемент пользовательской привязки можно добавить в эту коллекцию, используя ключевое слово `add`, присвоив атрибуту `type` элемента значение, соответствующее расширению элемента привязки, и указав в атрибуте `name` пользовательский элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="8b452-104">You can add a custom binding element to this collection by using the `add` keyword, and setting the `type` attribute of the element to a binding element extension, as well as the `name` attribute to the custom binding element.</span></span>  
  
 <span data-ttu-id="8b452-105">Расширения привязки позволяют пользователю создавать свои собственные элементы привязки и задействовать их как часть пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="8b452-105">Binding extensions enable the user to create user-defined binding elements for use as part of custom bindings.</span></span> <span data-ttu-id="8b452-106">Ну уровне программирования расширение привязки представляет собой тип, реализующий абстрактный класс <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="8b452-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="8b452-107">В файле конфигурации раздел `bindingElementExtensions` используется для определения элемента расширения.</span><span class="sxs-lookup"><span data-stu-id="8b452-107">In the configuration file, the `bindingElementExtensions` section is used to define an extension element.</span></span>  
  
 <span data-ttu-id="8b452-108">В следующем примере элемент `add` и атрибут `name` используются для добавления расширения привязки в раздел `bindingElementExtensions` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8b452-108">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingElementExtensions>  
           <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingElementExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="8b452-109">Чтобы добавить в элемент возможность настройки, пользователю следует записать и зарегистрировать элемент `bindingElementExtensionSection`.</span><span class="sxs-lookup"><span data-stu-id="8b452-109">To add configuration abilities to the element, the user needs to write and register a `bindingElementExtensionSection` element.</span></span> <span data-ttu-id="8b452-110">Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="8b452-110">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="8b452-111">После определения элемента и типа его конфигурации расширение можно использовать как часть пользовательской привязки (см. следующий пример).</span><span class="sxs-lookup"><span data-stu-id="8b452-111">After the element and its configuration type are defined, the extension can be used as part of a custom binding as shown in the following example.</span></span>  
  
```xml  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b452-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8b452-112">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>  
 [<span data-ttu-id="8b452-113">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8b452-113">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
