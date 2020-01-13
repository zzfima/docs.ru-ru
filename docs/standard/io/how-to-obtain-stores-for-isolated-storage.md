---
title: Практическое руководство. Получение хранилищ для изолированного хранения
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
ms.openlocfilehash: 7104ba665f60c2d55217a2d8628c85f6e469ad6f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706935"
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Практическое руководство. Получение хранилищ для изолированного хранения
Изолированное хранилище предоставляет виртуальную файловую систему в секции данных. Класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> предоставляет ряд методов для взаимодействия с изолированным хранилищем. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> содержит три статических метода, позволяющих создать и получить хранилище:  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> возвращает хранилище, изолированное по пользователю и сборке.  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> возвращает хранилище, изолированное по домену и сборке.  
  
     Хранилище, полученное любым из этих двух методов, принадлежит коду, из которого они вызваны.  
  
- Статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> возвращает изолированное хранилище, которое определяется комбинацией переданных параметров области.  
  
 Следующий код возвращает хранилище, изолированное по пользователю, сборке и домену.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Вы можете использовать метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>, чтобы определить перемещаемое хранилище для перемещаемого профиля пользователя. Дополнительные сведения о такой настройке см. в статье [о типах изоляции](../../../docs/standard/io/types-of-isolation.md).  
  
 Как очевидно из названия, изолированные хранилища из разных сборок являются разными хранилищами. Вы можете получить доступ к хранилищу другой сборки или другого домена, передав свидетельство сборки или домена в параметрах метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Для такого действия вам потребуются права на доступ к изолированному хранилищу по идентификатору домена приложения. Дополнительную информацию см. в описании перегрузок метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 Методы <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> возвращают объект <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Чтобы правильно выбрать тип изоляции для конкретного случая, изучите статью о [типах изоляции](../../../docs/standard/io/types-of-isolation.md). Получив объект файла изолированного хранилища, вы можете использовать методы изолированного хранилища для чтения, записи, создания и удаления файлов и каталогов в нем.  
  
 Не существует механизмов защиты, препятствующих передаче объекта <xref:System.IO.IsolatedStorage.IsolatedStorageFile> в код, который не имеет соответствующих прав для доступа к этому хранилищу. Идентификаторы доменов и сборок, а также разрешения для изолированного хранилища проверяются только при получении ссылки на объект <xref:System.IO.IsolatedStorage.IsolatedStorage>, то есть обычно в методах <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> или <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Таким образом, защита ссылок на объекты <xref:System.IO.IsolatedStorage.IsolatedStorageFile> возлагается на код, использующий такие ссылки.  
  
## <a name="example"></a>Пример  
 Ниже приведен простой пример класса, который получает хранилище, изолированное по пользователю и сборке. Чтобы получить хранилище, изолированное по пользователю, домену и сборке, измените приведенный код, добавив <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> в аргументы, которые передает метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 Когда выполните этот код, проверьте успешно ли создано хранилище. Для этого введите в командной строке команду **StoreAdm /LIST**. Она запустит [средство изолированного хранилища (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) и выведет полный список выделенных пользователю изолированных хранилищ.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
- [Типы изоляции](../../../docs/standard/io/types-of-isolation.md)
- [Сборки в .NET](../assembly/index.md)
