---
title: "Типы изоляции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET Framework], isolated storage
- assemblies [.NET Framework], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6b07c090a381925f5330a820214126a121d3790b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-isolation"></a>Типы изоляции
Доступ к изолированному хранилищу всегда имеет только пользователь, который ее создал. Для реализации такого типа изоляции, общеязыковая среда выполнения использует то же обозначение удостоверение пользователя, который распознается операционной системы, удостоверение, связанных с процессом, в которой выполняется код при открытии хранилища. Удостоверение является удостоверение пользователя, прошедшего проверку подлинности, но олицетворения может вызвать идентификатора текущего пользователя динамическое изменение.  
  
 Доступ к изолированному хранилищу также ограничивается в соответствии с идентификатором, связанным с доменом приложения и сборкой или со сборкой. Среда выполнения получает идентификаторы следующими способами:  
  
-   Идентификатор домена представляет свидетельство в приложение, которое в случае веб-приложения может быть полный URL-адрес. Для кода, запускаемого оболочки удостоверение домена может основываться на путь к каталогу приложения. Например если исполняемый файл выполняется по пути C:\Office\MyApp.exe, удостоверение домена будет C:\Office\MyApp.exe.  
  
-   Удостоверение сборки является свидетельство сборки. Это может быть получено из криптографической цифровой подписи, который может быть сборки [строгого имени](../../../docs/framework/app-domains/strong-named-assemblies.md), сборки или его идентификатор URL-адреса издателя программного обеспечения. Если сборка имеет строгое имя и идентификатор издателя, то будет использоваться удостоверение издателя программного обеспечения. Если сборка получена из Интернета и не имеет подписи, используется идентификатор URL-адреса. Дополнительные сведения о сборках и строгих имен см. в разделе [программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
-   Перемещаемые хранилища перемещаются с пользователем, который имеет перемещаемый профиль пользователя. Файлы записываются в сетевую папку и загружаются для любого компьютера, к которому подключается пользователь. Дополнительные сведения о перемещаемых профилях пользователей см. в разделе <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Объединив понятия пользователя, домена и удостоверение сборки, изолированное хранилище можно изолировать данные следующими способами, каждый из которых имеет свои собственные сценарии использования:  
  
-   [Изоляция по пользователям и сборкам](#UserAssembly)  
  
-   [Изоляция по пользователю, домену и сборке](#UserDomainAssembly)  
  
 Каждый из этих способов изоляции можно объединить с перемещаемым профилем пользователя. Дополнительные сведения см. в разделе [изолированного хранилища и перемещаемые](#Roaming).  
  
 На следующем рисунке показано, как изоляция хранилищ в разных областях.  
  
 ![Изоляция по пользователям и сборкам](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
Типы изолированного хранения  
  
 Обратите внимание, что за исключением перемещаемых хранилищ, изолированное хранилище всегда неявно изолируются компьютером, так как он использует средства хранения, являющиеся локальными для данного компьютера.  
  
> [!IMPORTANT]
>  Изолированное хранилище недоступно для приложений Windows [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Вместо этого используйте классы данных приложений в пространствах имен `Windows.Storage` , включенных в API [!INCLUDE[wrt](../../../includes/wrt-md.md)] для хранения локальных данных и файлов. Дополнительные сведения см. в статье [Доступ к данным приложения](http://go.microsoft.com/fwlink/?LinkId=229175) в Центре разработки для Windows.  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a>Изоляция по пользователям и сборкам  
 Изоляция по пользователям и сборкам подходит, если сборки, которая использует данные хранение должна быть доступна из любого домена приложения. Как правило в этом случае изолированное хранилище используется для хранения данных, используемого несколькими приложениями, который не привязан к любого приложения, такие как имя пользователя или сведения о лицензиях. Для доступа к хранилищу, изолированного по пользователю и сборке, код должен быть доверенным для передачи данных между приложениями. Как правило изоляция по пользователям и сборкам разрешена в интрасетях, но не в Интернете. Вызов статического <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> метода и передачи пользователь и сборки <xref:System.IO.IsolatedStorage.IsolatedStorageScope> возвращает хранилище с этим типом изоляции.  
  
 В следующем примере кода извлекается хранилища, изолированного по пользователю и сборке. Хранилище может осуществляться через `isoFile` объекта.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Пример, использующий параметры свидетельства см. в разделе <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> Метод доступен для быстрого вызова, как показано в следующем примере кода. Это сочетание клавиш не может использоваться для открытия хранилищ, способных перемещаться. использовать <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> в таких случаях.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a>Изоляция по пользователю, домену и сборке  
 Если приложение использует сторонней сборке, которая требует закрытого хранения данных, могут использовать изолированное хранилище для хранения личных данных. Изоляция по пользователю, домену и сборке гарантирует, что только код в определенной сборке может обращаться к данным и только в том случае, если сборка используется программой, которая была запущена в момент создания сборкой хранилища, и только в том случае, когда пользователь, для которого было создано хранилище работает  приложение. Изоляция по пользователю, домену и сборке сохраняет сторонней сборке от утечки данных другим приложениям. Этот тип изоляции следует использовать по умолчанию, если нужно использовать изолированное хранилище, но не уверены какой тип изоляции для использования. Вызов статического <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile> и передается пользователю, домену и сборке <xref:System.IO.IsolatedStorage.IsolatedStorageScope> возвращает хранилище с этим типом изоляции.  
  
 В следующем примере кода извлекается хранилища, изолированного по пользователю, домену и сборке. Хранилище может осуществляться через `isoFile` объекта.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Другой метод доступна как ярлык, как показано в следующем примере кода. Это сочетание клавиш не может использоваться для открытия хранилищ, способных перемещаться. использовать <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> в таких случаях.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a>Изолированное хранение и перемещение  
 Перемещаемые профили пользователя — это функция Windows, которая позволяет пользователю настроить свой идентификатор в сети и использовать его для входа на любой сетевой компьютер с применением всех персональных настроек. Сборки, которую использует изолированное хранилище можно указать, что изолированное хранилище пользователя должно перемещаться с перемещаемым профилем пользователя. Роуминг может использоваться в сочетании с изоляция по пользователям и сборкам или с изоляцией по пользователю, домену и сборке. Если перемещаемый области не используется, хранилища не будут перемещаться, даже при использовании перемещаемого профиля пользователя.  
  
 В следующем примере кода извлекается перемещаемого хранилища, изолированного по пользователю и сборке. Хранилище может осуществляться через `isoFile` объекта.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Для создания перемещаемого хранилища, изолированного по пользователю, домену и приложения, можно добавить область домена. Это показано в следующем примере кода.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
