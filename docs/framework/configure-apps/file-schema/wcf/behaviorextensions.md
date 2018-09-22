---
title: '&lt;behaviorExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: d025497956715913923e839cb6c482f44f96babb
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576857"
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="93f0d-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="93f0d-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="93f0d-103">Расширения поведений позволяют пользователям создавать пользовательские элементы поведений.</span><span class="sxs-lookup"><span data-stu-id="93f0d-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="93f0d-104">Эти элементы могут использоваться вместе со стандартными элементами поведений Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="93f0d-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="93f0d-105">В разделе `behaviorExtensions` определяется элемент, который может использоваться в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="93f0d-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="93f0d-106">Далее приведен пример типичного расширения поведения.</span><span class="sxs-lookup"><span data-stu-id="93f0d-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="93f0d-107">Чтобы добавить в элемент возможности конфигурации, нужно записать и зарегистрировать элемент конфигурации.</span><span class="sxs-lookup"><span data-stu-id="93f0d-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="93f0d-108">Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="93f0d-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="93f0d-109">После определения элемента и его типа конфигурации поведение можно использовать, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="93f0d-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a><span data-ttu-id="93f0d-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="93f0d-110">Security</span></span>  
 <span data-ttu-id="93f0d-111">Настоятельно рекомендуется использовать полные имена сборок при регистрации типов в файлах `machine.config` и `app.config`.</span><span class="sxs-lookup"><span data-stu-id="93f0d-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="93f0d-112">Если тип определен неоднозначно, загрузчик типов среды CLR ищет его в следующих местоположениях в заданном порядке:</span><span class="sxs-lookup"><span data-stu-id="93f0d-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="93f0d-113">Если сборка типа известна, загрузчик ищет в местах перенаправления файла конфигурации, в глобальном кэше сборок, в текущей сборке, используя данные конфигурации, и в базовой папке приложения.</span><span class="sxs-lookup"><span data-stu-id="93f0d-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="93f0d-114">Если сборка неизвестна, загрузчик ищет в текущей сборке, в библиотеке mscorlib и в месте, возвращаемом обработчиком событий `TypeResolve`.</span><span class="sxs-lookup"><span data-stu-id="93f0d-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="93f0d-115">Порядок поиска в среде CLR может быть изменен с помощью таких средств, как механизм пересылки типа и событие AppDomain.TypeResolve.</span><span class="sxs-lookup"><span data-stu-id="93f0d-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="93f0d-116">Злоумышленник может использовать порядок поиска в среде CLR и выполнить неавторизованный код.</span><span class="sxs-lookup"><span data-stu-id="93f0d-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="93f0d-117">Использование полных (строгих) имен однозначно идентифицирует тип и еще больше повышает безопасность системы.</span><span class="sxs-lookup"><span data-stu-id="93f0d-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="93f0d-118">Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](https://go.microsoft.com/fwlink/?LinkId=95336) и <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="93f0d-118">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f0d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="93f0d-119">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [<span data-ttu-id="93f0d-120">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="93f0d-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
