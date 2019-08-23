---
title: Практическое руководство. Создание базового RSS-канала
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
ms.openlocfilehash: 9a07754e8fdad700bd5488f392f80b5c5f907f6e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968442"
---
# <a name="how-to-create-a-basic-rss-feed"></a>Практическое руководство. Создание базового RSS-канала
Windows Communication Foundation (WCF) позволяет создать службу, предоставляющую канал синдикации. В данном разделе рассматривается процесс создания службы синдикации, предоставляющей веб-канал синдикации RSS.  
  
### <a name="to-create-a-basic-syndication-service"></a>Создание базовой службы синдикации  
  
1. Определите контракт службы с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>. Каждая операция, предоставляемая как веб-канал синдикации, должна возвращать объект <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>.  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    > Все операции службы, применяющие атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, сопоставляются с запросами HTTP GET. Чтобы сопоставить операцию с другим методом HTTP, используйте <xref:System.ServiceModel.Web.WebInvokeAttribute>. Дополнительные сведения см. в разделе [Практическое руководство. Создайте базовую веб-службу](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)HTTP WCF.  
  
2. Реализуйте контракт службы.  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3. Создайте объект <xref:System.ServiceModel.Syndication.SyndicationFeed>, затем добавьте автора, категорию и описание.  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4. Создайте несколько объектов <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5. Добавьте <xref:System.ServiceModel.Syndication.SyndicationItem> в веб-канал.  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6. Возвратите веб-канал.  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### <a name="to-host-a-service"></a>Размещение службы  
  
1. Создание объекта <xref:System.ServiceModel.Web.WebServiceHost>.  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2. Откройте узел службы и подождите, пока пользователь не нажмет клавишу ВВОД.  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>Вызов GetBlog() c HTTP GET  
  
1. Откройте Internet Explorer, введите следующий URL-адрес и нажмите клавишу `http://localhost:8000/BlogService/GetBlog`ввод:. URL-адрес содержит базовый адрес службы (`http://localhost:8000/BlogService`), относительный адрес конечной точки и операцию службы для вызова.  
  
### <a name="to-call-getblog-from-code"></a>Вызов GetBlog() из кода  
  
1. Создайте <xref:System.Xml.XmlReader> с базовым адресом и вызываемым методом.  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2. Вызовите статический метод <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, передав ему только что созданный объект <xref:System.Xml.XmlReader>.  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     Это вызывает операцию службы и заполняет новый <xref:System.ServiceModel.Syndication.SyndicationFeed> с помощью модуля форматирования, возвращенного от операции службы.  
  
3. Откройте объект веб-канала.  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## <a name="example"></a>Пример  
 Ниже приведен полный код этого примера.  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 При компиляции приведенного выше кода задайте ссылки на файлы System.ServiceModel.dll и System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
