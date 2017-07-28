---
title: "Практическое руководство. Перечисление хранилищ для изолированного хранилища | Microsoft Docs"
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
  - "перечисление хранилищ"
  - "хранение данных с помощью изолированного хранилища, перечисление хранилищ"
  - "сохранение данных с помощью изолированного хранилища, перечисление хранилищ"
  - "хранилища, перечисление"
  - "изолированное хранилище, перечисление"
  - "хранилища данных, перечисление"
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Перечисление хранилищ для изолированного хранилища
Перечислить все изолированные хранилища для текущего пользователя можно с помощью статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=fullName>.  Данный метод принимает значение <xref:System.IO.IsolatedStorage.IsolatedStorageScope> и возвращает перечислитель <xref:System.IO.IsolatedStorage.IsolatedStorageFile>.  Чтобы перечислить хранилища, необходимо иметь разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission> с указанным значением <xref:System.Security.Permissions.IsolatedStorageContainment>.  Если вызвать метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> со значением <xref:System.IO.IsolatedStorage.IsolatedStorageScope>, то он вернет массив объектов <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, определенных для текущего пользователя.  
  
## Пример  
 В следующем примере кода будет получено хранилище, которое изолировано по пользователю и сборке, создано несколько файлов и эти файлы будут извлечены с помощью метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)