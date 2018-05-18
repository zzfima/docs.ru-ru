---
title: Практическое руководство. Добавление или удаление записей списка управления доступом
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24c428a80f18b35d0aa3119a3c5fa1a6dcb2130e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a>Практическое руководство. Добавление или удаление записей списка управления доступом
Для добавления записей списка управления доступом (ACL) в файл или удаления из него необходимо получить объект <xref:System.Security.AccessControl.FileSecurity> или <xref:System.Security.AccessControl.DirectorySecurity> из файла или каталога, изменить его и затем применить обратно к файлу или каталогу.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a>Добавление или удаление элемента списка ACL из файла  
  
1.  Вызовите метод <xref:System.IO.File.GetAccessControl%2A> для получения объекта <xref:System.Security.AccessControl.FileSecurity>, содержащего текущие элементы списка ACL файла.  
  
2.  Добавьте и удалите элементы списка ACL из объекта <xref:System.Security.AccessControl.FileSecurity>, возвращенного в шаге 1.  
  
3.  Передайте объект <xref:System.Security.AccessControl.FileSecurity> в метод <xref:System.IO.File.SetAccessControl%2A>, чтобы применить изменения.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a>Добавление или удаление элемента списка ACL из каталога  
  
1.  Вызовите метод <xref:System.IO.Directory.GetAccessControl%2A> для получения объекта <xref:System.Security.AccessControl.DirectorySecurity>, содержащего текущие элементы списка ACL каталога.  
  
2.  Добавьте и удалите элементы списка ACL из объекта <xref:System.Security.AccessControl.DirectorySecurity>, возвращенного в шаге 1.  
  
3.  Передайте объект <xref:System.Security.AccessControl.DirectorySecurity> в метод <xref:System.IO.Directory.SetAccessControl%2A>, чтобы применить изменения.  
  
## <a name="example"></a>Пример  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для выполнения этого примера необходимо указать допустимую учетную запись пользователя или группы. В этом примере используется объект <xref:System.IO.File>; однако та же самая процедура используется для классов <xref:System.IO.FileInfo>, <xref:System.IO.Directory> и <xref:System.IO.DirectoryInfo>.
