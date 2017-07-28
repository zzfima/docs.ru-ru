---
title: "Типы изоляции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сохранение данных с помощью изолированного хранилища, доступ к изолированному хранилищу"
  - "сохранение данных с помощью изолированного хранилища, типы изоляции"
  - "проверка подлинности [платформа .NET Framework], изолированное хранилище"
  - "сборки [платформа .NET Framework], удостоверение"
  - "изолированное хранилище, доступ"
  - "хранение данных с помощью изолированного хранилища, типы изоляции"
  - "хранение данных с помощью изолированного хранилища, доступ к изолированному хранилищу"
  - "идентификатор домена"
  - "изолированное хранилище, типы"
  - "проверка подлинности пользователя, изолированное хранилище"
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Типы изоляции
Доступ к изолированному хранилищу всегда имеет только пользователь, создавший его.  Для реализации такого типа изоляции среда CLR использует то же обозначение идентификатора пользователя, которое распознает операционная система. Этот идентификатор привязан к процессу, в котором выполняется код, когда хранилище открыто.  Такой идентификатор является подтвержденным идентификатором пользователя, однако олицетворение может вызвать динамическое изменение идентификатора текущего пользователя.  
  
 Также доступ к изолированному хранилищу ограничивается в соответствии с идентификатором, связанным с доменом приложения и сборкой или только со сборкой.  Среда выполнения получает идентификаторы следующими способами.  
  
-   Идентификатор домена представляет собой свидетельство приложения, которым в случае веб\-приложения может быть полный URL\-адрес.  Для кода, запускаемого из той же оболочки, идентификатором домена может служить путь к каталогу приложения.  Например, если исполняемый код запускается из приложения "C:\\Office\\MyApp.exe", то идентификатором домена будет "C:\\Office\\MyApp.exe".  
  
-   Идентификатор сборки — это свидетельство сборки.  Оно может быть получено из криптографической цифровой подписи, которой может являться [строгое имя](../../../docs/framework/app-domains/strong-named-assemblies.md) сборки, ее издатель или идентификатор URL\-адреса.  Если у сборки есть и строгое имя, и идентификатор издателя, то используется последний.  Если сборка получена через Интернет и у нее нет подписи, используется идентификатор URL\-адреса.  Дополнительные сведения о сборках и строгих именах см. в разделе [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
-   Перемещаемые хранилища перемещаются вместе с пользователями, у которых есть перемещаемые профили.  Файлы записываются в сетевой каталог и передаются на любой компьютер, к которому подключается пользователь.  Дополнительные сведения о перемещаемом профиле пользователя см. в разделе <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName>.  
  
 Совмещая принципы идентификации пользователей, доменов и сборок, изолированное хранилище может отделять данные следующими способами, каждый из которых предусматривает свой сценарий применения:  
  
-   [Изоляция по пользователю и по сборке](#UserAssembly)  
  
-   [Изоляция по пользователю, домену и сборке](#UserDomainAssembly)  
  
 Каждый из этих способов изоляции может быть совмещен с перемещаемыми профилями пользователей.  Дополнительные сведения см. в разделе [Изолированное хранение и перемещение](#Roaming).  
  
 В следующем примере описывается изоляция хранилищ в различных контекстах.  
  
 ![Изоляция по пользователям и сборкам](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
Типы изолированных хранилищ  
  
 Обратите внимание, что за исключением случая перемещаемых хранилищ, изолированное хранилище всегда неявно изолировано компьютером, т.к. использует средства хранения конкретного компьютера.  
  
> [!IMPORTANT]
>  Изолированное хранилище не доступно для приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  Вместо этого используйте классы данных приложений в пространстве имен `Windows.Storage`, включенное в API [!INCLUDE[wrt](../../../includes/wrt-md.md)] для хранения локальных данных и файлов.  Дополнительные сведения см. в разделе [Данные приложения](http://go.microsoft.com/fwlink/?LinkId=229175) центра разработки для Windows.  
  
<a name="UserAssembly"></a>   
## Изоляция по пользователям и сборкам  
 Если сборка, использующая хранилище данных, должна быть доступна из любого домена приложения, целесообразно применение изоляции по пользователям и сборкам.  Обычно в такой ситуации изолированное хранение применяется для хранения данных, не привязанных к одному конкретному приложению и используемых несколькими приложениями, таких как имя пользователя или информация о лицензии.  Для доступа к хранилищу, изолированному по пользователям и сборкам, код должен иметь права на перемещение информации между приложениями.  Обычно изоляция по пользователям и сборкам разрешена в интрасетях, но не в Интернете.  Вызов статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=fullName> и передача в него пользователя, домена и сборки приводит к тому, что <xref:System.IO.IsolatedStorage.IsolatedStorageScope> возвращает хранилище с этим типом изоляции.  
  
 В следующем примере описывается получение перемещаемого хранилища, изолированного по пользователю и сборке.  Доступ к хранилищу может осуществляться через объект `isoFile` .  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Пример, использующий параметры свидетельства, см. в разделе <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 В качестве ярлыка может использоваться метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, приведенный в следующем примере кода.  Этот ярлык не может быть использован для открытия перемещаемого хранилища. В таких случаях используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## Изоляция по пользователям, доменам и сборкам  
 Если приложение использует сборку стороннего производителя, требующую закрытого хранения данных, то для этого может использоваться изолированное хранилище.  Изоляция по пользователям, доменам и сборкам обеспечивает доступность данных лишь для кода в данной сборке только в том случае, если сборка используется приложением, которое было запущено во время создания хранилища сборкой, и только если приложение запущено пользователем, для которого было создано хранилище.  Изоляция по пользователям, доменам и сборкам препятствует утечке данных в другие приложения через сборки третьей стороны.  Этот тип изоляции следует использовать по умолчанию, если необходимо использовать изолированное хранилище, но неизвестно, какой тип изоляции выбрать.  Вызов статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> класса <xref:System.IO.IsolatedStorage.IsolatedStorageFile> и передача в него пользователя, домена и сборки приводит к тому, что <xref:System.IO.IsolatedStorage.IsolatedStorageScope> возвращает хранилище с этим типом изоляции.  
  
 В следующем примере описывается получение хранилища, изолированного по пользователю, домену и сборке.  Доступ к хранилищу может осуществляться через объект `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 В качестве ярлыка может использоваться другой метод, приведенный в следующем примере кода.  Этот ярлык не может быть использован для открытия перемещаемого хранилища. В таких случаях используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## Изолированное хранение и перемещение  
 Перемещаемые профили пользователя — это функция Windows, позволяющая пользователю настроить свой идентификатор в сети и использовать его для входа на любой сетевой компьютер с применением всех персональных настроек.  Использующая изолированное хранение сборка может определять, что изолированное хранилище пользователя должно перемещаться вместе с перемещаемым профилем пользователя.  Перемещение может использоваться в сочетании с изоляцией по пользователям и сборкам или с изоляцией по пользователям, доменам и сборкам.  Если не применяется перемещаемая область действия, то хранилища не будут перемещаться, даже если задействованы перемещаемые профили пользователей.  
  
 В следующем примере описывается получение перемещаемого хранилища, изолированного по пользователю и сборке.  Доступ к хранилищу может осуществляться через объект `isoFile` .  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Для создания перемещаемого хранилища, изолированного по пользователю, домену и приложению, можно добавить область домена.  Это продемонстрировано в следующем примере.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)