---
title: Типы изоляции
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 99e1f3f96465d05c100a0dbb2bc5218810c33754
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159433"
---
# <a name="types-of-isolation"></a>Типы изоляции
Доступ к изолированному хранилищу всегда предоставляется только пользователю, который его создал. Чтобы поддерживать изоляцию такого типа, общеязыковая среда выполнения использует тот же подход к идентификации пользователя, что и операционная система, применяя идентификатор, связанный с процессом, в котором выполнялся код при открытии хранилища. Этот идентификатор обозначает аутентифицированного пользователя, но использование функции олицетворения может привести к тому, что идентификатор текущего пользователя изменится в ходе выполнения приложения.  
  
 Доступ к изолированному хранилищу также ограничивается идентификатором, связанным с доменом приложения и сборкой, или только со сборкой. Среда выполнения получает идентификаторы следующими способами:  
  
- Идентификатор домена является свидетельством приложения. Например, для веб-приложения это может быть полный URL-адрес. Для кода, запускаемого в оболочке, в качестве идентификатора домена может использовать путь к каталогу приложения. Например, если исполняемый файл размещается по пути C:\Office\MyApp.exe, для него будет установлен идентификатор домена "C:\Office\MyApp.exe".  
  
- Удостоверение сборки является свидетельством сборки. Оно может извлекаться из криптографической цифровой подписи, роль которой может выполнять [строгое имя](../assembly/strong-named.md) сборки, обозначение издателя программного обеспечения или идентификатор URL-адреса. Если сборка имеет и строгое имя, и идентификатор издателя программного обеспечения, то используется идентификатор издателя программного обеспечения. Если сборка получена из Интернета и не имеет подписи, используется идентификатор URL-адреса. Дополнительные сведения о сборках и строгих именах вы найдете в статье [Программирование с использованием сборок](../assembly/program.md).  
  
- Перемещаемые хранилища перемещаются с пользователем, который имеет перемещаемый профиль пользователя. Файлы записываются в сетевую папку и скачиваются на каждый компьютер, с которого этот пользователь выполняет вход. Дополнительные сведения о перемещаемых профилях пользователей см. в статье <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Объединяя концепции идентификаторов пользователя, домена и сборки, изолированное хранилище может изолировать данные несколькими разными способами, для каждого из которых есть применимые сценарии использования:  
  
- [изоляция по пользователям и сборкам](#UserAssembly);  
  
- [изоляция по пользователям, доменам и сборкам](#UserDomainAssembly).  
  
 Каждый из этих способов изоляции можно объединить с перемещаемым профилем пользователя. Дополнительные сведения см. в разделе об [изолированном хранении и перемещении](#Roaming).  
  
 На следующем изображении показано, как хранилища изолируются в разных областях:  
  
 ![Схема, показывающая изоляцию по пользователям и сборкам.](./media/types-of-isolation/isolated-storage-types.gif)  
  
 Обратите внимание, что изолированные хранилища, за исключением перемещаемых, всегда неявно изолируются по компьютерам, так как для них применяются локальные средства хранения конкретного компьютера.  
  
> [!IMPORTANT]
> Изолированное хранилище недоступно для приложений Магазина Windows 8.x. Вместо этого используйте классы данных приложений в пространствах имен `Windows.Storage`, включенных в API среды выполнения Windows для хранения локальных данных и файлов. Дополнительные сведения см. в статье [Доступ к данным приложения](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)) в Центре разработки для Windows.  
  
<a name="UserAssembly"></a>
## <a name="isolation-by-user-and-assembly"></a>Изоляция по пользователям и сборкам  
 Изоляция по пользователям и сборкам подходит в тех случаях, когда использующая это хранилище сборка должна быть доступна из любого домена приложения. Обычно таким образом изолированное хранилище используется для хранения данных, применяющихся в несколькими приложениях и не привязанных к любому из них, например имен пользователей и (или) сведений о лицензиях. Для доступа к хранилищу, изолированному по пользователю и сборке, код должен иметь доверие на передачу данных между приложениями. Как правило, изоляция по пользователям и сборкам допускается только в интрасетях, но не в Интернете. Чтобы получить хранилище с этим типом изоляции, вызовите статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> и передайте в него <xref:System.IO.IsolatedStorage.IsolatedStorageScope> с указанием пользователя и сборки.  
  
 Приведенный ниже код возвращает хранилище, изолированное по пользователю, сборке и домену. Доступ к этому хранилищу можно осуществлять через объект `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Пример использования параметров свидетельства см. в разделе <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 Можно также использовать метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, как показано в следующем примере кода. Этот упрощенный вариант не позволяет открывать хранилища с поддержкой перемещения. В таких случаях используется <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>
## <a name="isolation-by-user-domain-and-assembly"></a>Изоляция по пользователям, доменам и сборкам  
 Если приложение использует сборку стороннего поставщика, для которой нужно закрытое хранилище данных, вы можете применить изолированное хранилище. Изоляция по пользователям, доменам и сборкам гарантирует, что доступ к данным получит только код из определенной сборки и только в том случае, если эту сборку использует приложение, запущенное в момент создания хранилища. Это приложение должно работать от имени пользователя, для которого было создано хранилище. Изоляция по пользователям, доменам и сборкам не позволяет сторонним сборкам влиять на данные других приложений. По умолчанию следует использовать именно этот тип изоляции, если вы намерены использовать изолированное хранилище, но не уверены в выборе его типа. Чтобы получить хранилище с этим типом изоляции, вызовите статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> из <xref:System.IO.IsolatedStorage.IsolatedStorageFile> и передайте в него <xref:System.IO.IsolatedStorage.IsolatedStorageScope> с указанием пользователя, домена и сборки.  
  
 После выполнения приведенного ниже кода возвращается хранилище, изолированное по пользователю, домену и сборке. Доступ к этому хранилищу можно осуществлять через объект `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Можно использовать другой метод, как показано в приведенном ниже примере кода. Этот упрощенный вариант не позволяет открывать хранилища с поддержкой перемещения. В таких случаях используется <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>
## <a name="isolated-storage-and-roaming"></a>Изолированное хранилище и роуминг  
 Перемещаемые профили пользователя — это функция Windows, которая позволяет пользователю настроить и использовать сетевой идентификатор, чтобы при входе на любой сетевой компьютер применялись одинаковые персональные настройки. Сборка, которая использует изолированное хранилище, может потребовать переноса изолированного хранилища вместе с перемещаемым профилем пользователя. Роуминг можно использовать в сочетании с изоляцией по пользователям и сборкам или с изоляцией по пользователям, доменам и сборкам. Если функция перемещения не используется, хранилище будет сохраняться только локально даже для пользователей с перемещаемым профилем.  
  
 После выполнения приведенного ниже кода возвращается перемещаемое хранилище, изолированное по пользователю и сборке. Доступ к этому хранилищу можно осуществлять через объект `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Добавив к нему область домена, вы получите перемещаемое хранилище, изолированное по пользователю, домену и приложению. Это действие представлено в следующем примере кода:  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
