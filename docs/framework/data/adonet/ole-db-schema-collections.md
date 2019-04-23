---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164688"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="2db11-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="2db11-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="2db11-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="2db11-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="2db11-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="2db11-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="2db11-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="2db11-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="2db11-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="2db11-106">Tables</span></span>  
  
-   <span data-ttu-id="2db11-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2db11-107">Columns</span></span>  
  
-   <span data-ttu-id="2db11-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2db11-108">Procedures</span></span>  
  
-   <span data-ttu-id="2db11-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2db11-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="2db11-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="2db11-110">Catalog</span></span>  
  
-   <span data-ttu-id="2db11-111">Индексы</span><span class="sxs-lookup"><span data-stu-id="2db11-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2db11-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="2db11-112">Tables</span></span>  
  
|<span data-ttu-id="2db11-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-113">ColumnName</span></span>|<span data-ttu-id="2db11-114">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-115">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-116">String</span><span class="sxs-lookup"><span data-stu-id="2db11-116">String</span></span>|  
|<span data-ttu-id="2db11-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-118">String</span><span class="sxs-lookup"><span data-stu-id="2db11-118">String</span></span>|  
|<span data-ttu-id="2db11-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-119">TABLE_NAME</span></span>|<span data-ttu-id="2db11-120">String</span><span class="sxs-lookup"><span data-stu-id="2db11-120">String</span></span>|  
|<span data-ttu-id="2db11-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-121">TABLE_TYPE</span></span>|<span data-ttu-id="2db11-122">String</span><span class="sxs-lookup"><span data-stu-id="2db11-122">String</span></span>|  
|<span data-ttu-id="2db11-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-123">TABLE_GUID</span></span>|<span data-ttu-id="2db11-124">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-124">Guid</span></span>|  
|<span data-ttu-id="2db11-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-125">DESCRIPTION</span></span>|<span data-ttu-id="2db11-126">String</span><span class="sxs-lookup"><span data-stu-id="2db11-126">String</span></span>|  
|<span data-ttu-id="2db11-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-127">TABLE_PROPID</span></span>|<span data-ttu-id="2db11-128">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-128">Int64</span></span>|  
|<span data-ttu-id="2db11-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-129">DATE_CREATED</span></span>|<span data-ttu-id="2db11-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-130">DateTime</span></span>|  
|<span data-ttu-id="2db11-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-131">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2db11-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2db11-133">Columns</span></span>  
  
|<span data-ttu-id="2db11-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-134">ColumnName</span></span>|<span data-ttu-id="2db11-135">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-136">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-137">String</span><span class="sxs-lookup"><span data-stu-id="2db11-137">String</span></span>|  
|<span data-ttu-id="2db11-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-139">String</span><span class="sxs-lookup"><span data-stu-id="2db11-139">String</span></span>|  
|<span data-ttu-id="2db11-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-140">TABLE_NAME</span></span>|<span data-ttu-id="2db11-141">String</span><span class="sxs-lookup"><span data-stu-id="2db11-141">String</span></span>|  
|<span data-ttu-id="2db11-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-142">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-143">String</span><span class="sxs-lookup"><span data-stu-id="2db11-143">String</span></span>|  
|<span data-ttu-id="2db11-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-144">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-145">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-145">Guid</span></span>|  
|<span data-ttu-id="2db11-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-146">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-147">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-147">Int64</span></span>|  
|<span data-ttu-id="2db11-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-149">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-149">Int64</span></span>|  
|<span data-ttu-id="2db11-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2db11-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-151">Boolean</span></span>|  
|<span data-ttu-id="2db11-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2db11-153">String</span><span class="sxs-lookup"><span data-stu-id="2db11-153">String</span></span>|  
|<span data-ttu-id="2db11-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2db11-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="2db11-155">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-155">Int64</span></span>|  
|<span data-ttu-id="2db11-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-156">IS_NULLABLE</span></span>|<span data-ttu-id="2db11-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-157">Boolean</span></span>|  
|<span data-ttu-id="2db11-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-158">DATA_TYPE</span></span>|<span data-ttu-id="2db11-159">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-159">Int32</span></span>|  
|<span data-ttu-id="2db11-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-160">TYPE_GUID</span></span>|<span data-ttu-id="2db11-161">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-161">Guid</span></span>|  
|<span data-ttu-id="2db11-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2db11-163">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-163">Int64</span></span>|  
|<span data-ttu-id="2db11-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2db11-165">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-165">Int64</span></span>|  
|<span data-ttu-id="2db11-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2db11-167">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-167">Int32</span></span>|  
|<span data-ttu-id="2db11-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2db11-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="2db11-169">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-169">Int16</span></span>|  
|<span data-ttu-id="2db11-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="2db11-171">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-171">Int64</span></span>|  
|<span data-ttu-id="2db11-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2db11-173">String</span><span class="sxs-lookup"><span data-stu-id="2db11-173">String</span></span>|  
|<span data-ttu-id="2db11-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2db11-175">String</span><span class="sxs-lookup"><span data-stu-id="2db11-175">String</span></span>|  
|<span data-ttu-id="2db11-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2db11-177">String</span><span class="sxs-lookup"><span data-stu-id="2db11-177">String</span></span>|  
|<span data-ttu-id="2db11-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="2db11-179">String</span><span class="sxs-lookup"><span data-stu-id="2db11-179">String</span></span>|  
|<span data-ttu-id="2db11-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2db11-181">String</span><span class="sxs-lookup"><span data-stu-id="2db11-181">String</span></span>|  
|<span data-ttu-id="2db11-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-182">COLLATION_NAME</span></span>|<span data-ttu-id="2db11-183">String</span><span class="sxs-lookup"><span data-stu-id="2db11-183">String</span></span>|  
|<span data-ttu-id="2db11-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2db11-185">String</span><span class="sxs-lookup"><span data-stu-id="2db11-185">String</span></span>|  
|<span data-ttu-id="2db11-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2db11-187">String</span><span class="sxs-lookup"><span data-stu-id="2db11-187">String</span></span>|  
|<span data-ttu-id="2db11-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-188">DOMAIN_NAME</span></span>|<span data-ttu-id="2db11-189">String</span><span class="sxs-lookup"><span data-stu-id="2db11-189">String</span></span>|  
|<span data-ttu-id="2db11-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-190">DESCRIPTION</span></span>|<span data-ttu-id="2db11-191">String</span><span class="sxs-lookup"><span data-stu-id="2db11-191">String</span></span>|  
|<span data-ttu-id="2db11-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="2db11-192">COLUMN_LCID</span></span>|<span data-ttu-id="2db11-193">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-193">Int32</span></span>|  
|<span data-ttu-id="2db11-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="2db11-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="2db11-195">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-195">Int32</span></span>|  
|<span data-ttu-id="2db11-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="2db11-196">COLUMN_SORTID</span></span>|<span data-ttu-id="2db11-197">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-197">Int32</span></span>|  
|<span data-ttu-id="2db11-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="2db11-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="2db11-199">Byte[]</span></span>|  
|<span data-ttu-id="2db11-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="2db11-200">IS_COMPUTED</span></span>|<span data-ttu-id="2db11-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2db11-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2db11-202">Procedures</span></span>  
  
|<span data-ttu-id="2db11-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-203">ColumnName</span></span>|<span data-ttu-id="2db11-204">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2db11-206">String</span><span class="sxs-lookup"><span data-stu-id="2db11-206">String</span></span>|  
|<span data-ttu-id="2db11-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2db11-208">String</span><span class="sxs-lookup"><span data-stu-id="2db11-208">String</span></span>|  
|<span data-ttu-id="2db11-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="2db11-210">String</span><span class="sxs-lookup"><span data-stu-id="2db11-210">String</span></span>|  
|<span data-ttu-id="2db11-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2db11-212">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-212">Int16</span></span>|  
|<span data-ttu-id="2db11-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2db11-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2db11-214">String</span><span class="sxs-lookup"><span data-stu-id="2db11-214">String</span></span>|  
|<span data-ttu-id="2db11-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-215">DESCRIPTION</span></span>|<span data-ttu-id="2db11-216">String</span><span class="sxs-lookup"><span data-stu-id="2db11-216">String</span></span>|  
|<span data-ttu-id="2db11-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-217">DATE_CREATED</span></span>|<span data-ttu-id="2db11-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-218">DateTime</span></span>|  
|<span data-ttu-id="2db11-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-219">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="2db11-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2db11-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="2db11-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-222">ColumnName</span></span>|<span data-ttu-id="2db11-223">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2db11-225">String</span><span class="sxs-lookup"><span data-stu-id="2db11-225">String</span></span>|  
|<span data-ttu-id="2db11-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2db11-227">String</span><span class="sxs-lookup"><span data-stu-id="2db11-227">String</span></span>|  
|<span data-ttu-id="2db11-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="2db11-229">String</span><span class="sxs-lookup"><span data-stu-id="2db11-229">String</span></span>|  
|<span data-ttu-id="2db11-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-230">PARAMETER_NAME</span></span>|<span data-ttu-id="2db11-231">String</span><span class="sxs-lookup"><span data-stu-id="2db11-231">String</span></span>|  
|<span data-ttu-id="2db11-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-233">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-233">Int32</span></span>|  
|<span data-ttu-id="2db11-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="2db11-235">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-235">Int32</span></span>|  
|<span data-ttu-id="2db11-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="2db11-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-237">Boolean</span></span>|  
|<span data-ttu-id="2db11-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="2db11-239">String</span><span class="sxs-lookup"><span data-stu-id="2db11-239">String</span></span>|  
|<span data-ttu-id="2db11-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-240">IS_NULLABLE</span></span>|<span data-ttu-id="2db11-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-241">Boolean</span></span>|  
|<span data-ttu-id="2db11-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-242">DATA_TYPE</span></span>|<span data-ttu-id="2db11-243">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-243">Int32</span></span>|  
|<span data-ttu-id="2db11-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2db11-245">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-245">Int64</span></span>|  
|<span data-ttu-id="2db11-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2db11-247">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-247">Int64</span></span>|  
|<span data-ttu-id="2db11-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2db11-249">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-249">Int32</span></span>|  
|<span data-ttu-id="2db11-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2db11-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="2db11-251">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-251">Int16</span></span>|  
|<span data-ttu-id="2db11-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-252">DESCRIPTION</span></span>|<span data-ttu-id="2db11-253">String</span><span class="sxs-lookup"><span data-stu-id="2db11-253">String</span></span>|  
|<span data-ttu-id="2db11-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-254">TYPE_NAME</span></span>|<span data-ttu-id="2db11-255">String</span><span class="sxs-lookup"><span data-stu-id="2db11-255">String</span></span>|  
|<span data-ttu-id="2db11-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="2db11-257">String</span><span class="sxs-lookup"><span data-stu-id="2db11-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="2db11-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="2db11-258">Catalog</span></span>  
  
|<span data-ttu-id="2db11-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-259">ColumnName</span></span>|<span data-ttu-id="2db11-260">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-261">CATALOG_NAME</span></span>|<span data-ttu-id="2db11-262">String</span><span class="sxs-lookup"><span data-stu-id="2db11-262">String</span></span>|  
|<span data-ttu-id="2db11-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-263">DESCRIPTION</span></span>|<span data-ttu-id="2db11-264">String</span><span class="sxs-lookup"><span data-stu-id="2db11-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2db11-265">Индексы</span><span class="sxs-lookup"><span data-stu-id="2db11-265">Indexes</span></span>  
  
|<span data-ttu-id="2db11-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-266">ColumnName</span></span>|<span data-ttu-id="2db11-267">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-268">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-269">String</span><span class="sxs-lookup"><span data-stu-id="2db11-269">String</span></span>|  
|<span data-ttu-id="2db11-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-271">String</span><span class="sxs-lookup"><span data-stu-id="2db11-271">String</span></span>|  
|<span data-ttu-id="2db11-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-272">TABLE_NAME</span></span>|<span data-ttu-id="2db11-273">String</span><span class="sxs-lookup"><span data-stu-id="2db11-273">String</span></span>|  
|<span data-ttu-id="2db11-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-274">INDEX_CATALOG</span></span>|<span data-ttu-id="2db11-275">String</span><span class="sxs-lookup"><span data-stu-id="2db11-275">String</span></span>|  
|<span data-ttu-id="2db11-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="2db11-277">String</span><span class="sxs-lookup"><span data-stu-id="2db11-277">String</span></span>|  
|<span data-ttu-id="2db11-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-278">INDEX_NAME</span></span>|<span data-ttu-id="2db11-279">String</span><span class="sxs-lookup"><span data-stu-id="2db11-279">String</span></span>|  
|<span data-ttu-id="2db11-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2db11-280">PRIMARY_KEY</span></span>|<span data-ttu-id="2db11-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-281">Boolean</span></span>|  
|<span data-ttu-id="2db11-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2db11-282">UNIQUE</span></span>|<span data-ttu-id="2db11-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-283">Boolean</span></span>|  
|<span data-ttu-id="2db11-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2db11-284">CLUSTERED</span></span>|<span data-ttu-id="2db11-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-285">Boolean</span></span>|  
|<span data-ttu-id="2db11-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-286">TYPE</span></span>|<span data-ttu-id="2db11-287">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-287">Int32</span></span>|  
|<span data-ttu-id="2db11-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2db11-288">FILL_FACTOR</span></span>|<span data-ttu-id="2db11-289">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-289">Int32</span></span>|  
|<span data-ttu-id="2db11-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2db11-290">INITIAL_SIZE</span></span>|<span data-ttu-id="2db11-291">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-291">Int32</span></span>|  
|<span data-ttu-id="2db11-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="2db11-292">NULLS</span></span>|<span data-ttu-id="2db11-293">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-293">Int32</span></span>|  
|<span data-ttu-id="2db11-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2db11-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2db11-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-295">Boolean</span></span>|  
|<span data-ttu-id="2db11-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2db11-296">AUTO_UPDATE</span></span>|<span data-ttu-id="2db11-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-297">Boolean</span></span>|  
|<span data-ttu-id="2db11-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-298">NULL_COLLATION</span></span>|<span data-ttu-id="2db11-299">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-299">Int32</span></span>|  
|<span data-ttu-id="2db11-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-301">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-301">Int64</span></span>|  
|<span data-ttu-id="2db11-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-302">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-303">String</span><span class="sxs-lookup"><span data-stu-id="2db11-303">String</span></span>|  
|<span data-ttu-id="2db11-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-304">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-305">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-305">Guid</span></span>|  
|<span data-ttu-id="2db11-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-306">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-307">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-307">Int64</span></span>|  
|<span data-ttu-id="2db11-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-308">COLLATION</span></span>|<span data-ttu-id="2db11-309">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-309">Int16</span></span>|  
|<span data-ttu-id="2db11-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2db11-310">CARDINALITY</span></span>|<span data-ttu-id="2db11-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="2db11-311">Decimal</span></span>|  
|<span data-ttu-id="2db11-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="2db11-312">PAGES</span></span>|<span data-ttu-id="2db11-313">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-313">Int32</span></span>|  
|<span data-ttu-id="2db11-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2db11-314">FILTER_CONDITION</span></span>|<span data-ttu-id="2db11-315">String</span><span class="sxs-lookup"><span data-stu-id="2db11-315">String</span></span>|  
|<span data-ttu-id="2db11-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2db11-316">INTEGRATED</span></span>|<span data-ttu-id="2db11-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="2db11-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="2db11-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="2db11-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="2db11-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="2db11-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="2db11-320">Tables</span></span>  
  
-   <span data-ttu-id="2db11-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2db11-321">Columns</span></span>  
  
-   <span data-ttu-id="2db11-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2db11-322">Procedures</span></span>  
  
-   <span data-ttu-id="2db11-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2db11-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="2db11-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2db11-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="2db11-325">Представления</span><span class="sxs-lookup"><span data-stu-id="2db11-325">Views</span></span>  
  
-   <span data-ttu-id="2db11-326">Индексы</span><span class="sxs-lookup"><span data-stu-id="2db11-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2db11-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="2db11-327">Tables</span></span>  
  
|<span data-ttu-id="2db11-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-328">ColumnName</span></span>|<span data-ttu-id="2db11-329">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-330">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-331">String</span><span class="sxs-lookup"><span data-stu-id="2db11-331">String</span></span>|  
|<span data-ttu-id="2db11-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-333">String</span><span class="sxs-lookup"><span data-stu-id="2db11-333">String</span></span>|  
|<span data-ttu-id="2db11-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-334">TABLE_NAME</span></span>|<span data-ttu-id="2db11-335">String</span><span class="sxs-lookup"><span data-stu-id="2db11-335">String</span></span>|  
|<span data-ttu-id="2db11-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-336">TABLE_TYPE</span></span>|<span data-ttu-id="2db11-337">String</span><span class="sxs-lookup"><span data-stu-id="2db11-337">String</span></span>|  
|<span data-ttu-id="2db11-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-338">TABLE_GUID</span></span>|<span data-ttu-id="2db11-339">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-339">Guid</span></span>|  
|<span data-ttu-id="2db11-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-340">DESCRIPTION</span></span>|<span data-ttu-id="2db11-341">String</span><span class="sxs-lookup"><span data-stu-id="2db11-341">String</span></span>|  
|<span data-ttu-id="2db11-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-342">TABLE_PROPID</span></span>|<span data-ttu-id="2db11-343">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-343">Int64</span></span>|  
|<span data-ttu-id="2db11-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-344">DATE_CREATED</span></span>|<span data-ttu-id="2db11-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-345">DateTime</span></span>|  
|<span data-ttu-id="2db11-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-346">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2db11-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2db11-348">Columns</span></span>  
  
|<span data-ttu-id="2db11-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-349">ColumnName</span></span>|<span data-ttu-id="2db11-350">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-351">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-352">String</span><span class="sxs-lookup"><span data-stu-id="2db11-352">String</span></span>|  
|<span data-ttu-id="2db11-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-354">String</span><span class="sxs-lookup"><span data-stu-id="2db11-354">String</span></span>|  
|<span data-ttu-id="2db11-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-355">TABLE_NAME</span></span>|<span data-ttu-id="2db11-356">String</span><span class="sxs-lookup"><span data-stu-id="2db11-356">String</span></span>|  
|<span data-ttu-id="2db11-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-357">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-358">String</span><span class="sxs-lookup"><span data-stu-id="2db11-358">String</span></span>|  
|<span data-ttu-id="2db11-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-359">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-360">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-360">Guid</span></span>|  
|<span data-ttu-id="2db11-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-361">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-362">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-362">Int64</span></span>|  
|<span data-ttu-id="2db11-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-364">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-364">Int64</span></span>|  
|<span data-ttu-id="2db11-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2db11-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-366">Boolean</span></span>|  
|<span data-ttu-id="2db11-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2db11-368">String</span><span class="sxs-lookup"><span data-stu-id="2db11-368">String</span></span>|  
|<span data-ttu-id="2db11-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2db11-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="2db11-370">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-370">Int64</span></span>|  
|<span data-ttu-id="2db11-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-371">IS_NULLABLE</span></span>|<span data-ttu-id="2db11-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-372">Boolean</span></span>|  
|<span data-ttu-id="2db11-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-373">DATA_TYPE</span></span>|<span data-ttu-id="2db11-374">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-374">Int32</span></span>|  
|<span data-ttu-id="2db11-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-375">TYPE_GUID</span></span>|<span data-ttu-id="2db11-376">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-376">Guid</span></span>|  
|<span data-ttu-id="2db11-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2db11-378">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-378">Int64</span></span>|  
|<span data-ttu-id="2db11-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2db11-380">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-380">Int64</span></span>|  
|<span data-ttu-id="2db11-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2db11-382">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-382">Int32</span></span>|  
|<span data-ttu-id="2db11-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2db11-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="2db11-384">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-384">Int16</span></span>|  
|<span data-ttu-id="2db11-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="2db11-386">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-386">Int64</span></span>|  
|<span data-ttu-id="2db11-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2db11-388">String</span><span class="sxs-lookup"><span data-stu-id="2db11-388">String</span></span>|  
|<span data-ttu-id="2db11-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2db11-390">String</span><span class="sxs-lookup"><span data-stu-id="2db11-390">String</span></span>|  
|<span data-ttu-id="2db11-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2db11-392">String</span><span class="sxs-lookup"><span data-stu-id="2db11-392">String</span></span>|  
|<span data-ttu-id="2db11-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="2db11-394">String</span><span class="sxs-lookup"><span data-stu-id="2db11-394">String</span></span>|  
|<span data-ttu-id="2db11-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2db11-396">String</span><span class="sxs-lookup"><span data-stu-id="2db11-396">String</span></span>|  
|<span data-ttu-id="2db11-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-397">COLLATION_NAME</span></span>|<span data-ttu-id="2db11-398">String</span><span class="sxs-lookup"><span data-stu-id="2db11-398">String</span></span>|  
|<span data-ttu-id="2db11-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2db11-400">String</span><span class="sxs-lookup"><span data-stu-id="2db11-400">String</span></span>|  
|<span data-ttu-id="2db11-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2db11-402">String</span><span class="sxs-lookup"><span data-stu-id="2db11-402">String</span></span>|  
|<span data-ttu-id="2db11-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-403">DOMAIN_NAME</span></span>|<span data-ttu-id="2db11-404">String</span><span class="sxs-lookup"><span data-stu-id="2db11-404">String</span></span>|  
|<span data-ttu-id="2db11-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-405">DESCRIPTION</span></span>|<span data-ttu-id="2db11-406">String</span><span class="sxs-lookup"><span data-stu-id="2db11-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2db11-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2db11-407">Procedures</span></span>  
  
|<span data-ttu-id="2db11-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-408">ColumnName</span></span>|<span data-ttu-id="2db11-409">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2db11-411">String</span><span class="sxs-lookup"><span data-stu-id="2db11-411">String</span></span>|  
|<span data-ttu-id="2db11-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2db11-413">String</span><span class="sxs-lookup"><span data-stu-id="2db11-413">String</span></span>|  
|<span data-ttu-id="2db11-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="2db11-415">String</span><span class="sxs-lookup"><span data-stu-id="2db11-415">String</span></span>|  
|<span data-ttu-id="2db11-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2db11-417">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-417">Int16</span></span>|  
|<span data-ttu-id="2db11-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2db11-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2db11-419">String</span><span class="sxs-lookup"><span data-stu-id="2db11-419">String</span></span>|  
|<span data-ttu-id="2db11-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-420">DESCRIPTION</span></span>|<span data-ttu-id="2db11-421">String</span><span class="sxs-lookup"><span data-stu-id="2db11-421">String</span></span>|  
|<span data-ttu-id="2db11-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-422">DATE_CREATED</span></span>|<span data-ttu-id="2db11-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-423">DateTime</span></span>|  
|<span data-ttu-id="2db11-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-424">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="2db11-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2db11-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="2db11-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-427">ColumnName</span></span>|<span data-ttu-id="2db11-428">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2db11-430">String</span><span class="sxs-lookup"><span data-stu-id="2db11-430">String</span></span>|  
|<span data-ttu-id="2db11-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2db11-432">String</span><span class="sxs-lookup"><span data-stu-id="2db11-432">String</span></span>|  
|<span data-ttu-id="2db11-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="2db11-434">String</span><span class="sxs-lookup"><span data-stu-id="2db11-434">String</span></span>|  
|<span data-ttu-id="2db11-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-435">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-436">String</span><span class="sxs-lookup"><span data-stu-id="2db11-436">String</span></span>|  
|<span data-ttu-id="2db11-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-437">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-438">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-438">Guid</span></span>|  
|<span data-ttu-id="2db11-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-439">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-440">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-440">Int64</span></span>|  
|<span data-ttu-id="2db11-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="2db11-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="2db11-442">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-442">Int64</span></span>|  
|<span data-ttu-id="2db11-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-444">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-444">Int64</span></span>|  
|<span data-ttu-id="2db11-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-445">IS_NULLABLE</span></span>|<span data-ttu-id="2db11-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-446">Boolean</span></span>|  
|<span data-ttu-id="2db11-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-447">DATA_TYPE</span></span>|<span data-ttu-id="2db11-448">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-448">Int32</span></span>|  
|<span data-ttu-id="2db11-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-449">TYPE_GUID</span></span>|<span data-ttu-id="2db11-450">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-450">Guid</span></span>|  
|<span data-ttu-id="2db11-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2db11-452">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-452">Int64</span></span>|  
|<span data-ttu-id="2db11-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2db11-454">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-454">Int64</span></span>|  
|<span data-ttu-id="2db11-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2db11-456">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-456">Int32</span></span>|  
|<span data-ttu-id="2db11-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2db11-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="2db11-458">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-458">Int16</span></span>|  
|<span data-ttu-id="2db11-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-459">DESCRIPTION</span></span>|<span data-ttu-id="2db11-460">String</span><span class="sxs-lookup"><span data-stu-id="2db11-460">String</span></span>|  
|<span data-ttu-id="2db11-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="2db11-461">OVERLOAD</span></span>|<span data-ttu-id="2db11-462">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2db11-463">Представления</span><span class="sxs-lookup"><span data-stu-id="2db11-463">Views</span></span>  
  
|<span data-ttu-id="2db11-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-464">ColumnName</span></span>|<span data-ttu-id="2db11-465">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-466">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-467">String</span><span class="sxs-lookup"><span data-stu-id="2db11-467">String</span></span>|  
|<span data-ttu-id="2db11-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-469">String</span><span class="sxs-lookup"><span data-stu-id="2db11-469">String</span></span>|  
|<span data-ttu-id="2db11-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-470">TABLE_NAME</span></span>|<span data-ttu-id="2db11-471">String</span><span class="sxs-lookup"><span data-stu-id="2db11-471">String</span></span>|  
|<span data-ttu-id="2db11-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2db11-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="2db11-473">String</span><span class="sxs-lookup"><span data-stu-id="2db11-473">String</span></span>|  
|<span data-ttu-id="2db11-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-474">CHECK_OPTION</span></span>|<span data-ttu-id="2db11-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-475">Boolean</span></span>|  
|<span data-ttu-id="2db11-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-476">IS_UPDATABLE</span></span>|<span data-ttu-id="2db11-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-477">Boolean</span></span>|  
|<span data-ttu-id="2db11-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-478">DESCRIPTION</span></span>|<span data-ttu-id="2db11-479">String</span><span class="sxs-lookup"><span data-stu-id="2db11-479">String</span></span>|  
|<span data-ttu-id="2db11-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-480">DATE_CREATED</span></span>|<span data-ttu-id="2db11-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-481">DateTime</span></span>|  
|<span data-ttu-id="2db11-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-482">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2db11-484">Индексы</span><span class="sxs-lookup"><span data-stu-id="2db11-484">Indexes</span></span>  
  
|<span data-ttu-id="2db11-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-485">ColumnName</span></span>|<span data-ttu-id="2db11-486">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-487">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-488">String</span><span class="sxs-lookup"><span data-stu-id="2db11-488">String</span></span>|  
|<span data-ttu-id="2db11-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-490">String</span><span class="sxs-lookup"><span data-stu-id="2db11-490">String</span></span>|  
|<span data-ttu-id="2db11-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-491">TABLE_NAME</span></span>|<span data-ttu-id="2db11-492">String</span><span class="sxs-lookup"><span data-stu-id="2db11-492">String</span></span>|  
|<span data-ttu-id="2db11-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-493">INDEX_CATALOG</span></span>|<span data-ttu-id="2db11-494">String</span><span class="sxs-lookup"><span data-stu-id="2db11-494">String</span></span>|  
|<span data-ttu-id="2db11-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="2db11-496">String</span><span class="sxs-lookup"><span data-stu-id="2db11-496">String</span></span>|  
|<span data-ttu-id="2db11-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-497">INDEX_NAME</span></span>|<span data-ttu-id="2db11-498">String</span><span class="sxs-lookup"><span data-stu-id="2db11-498">String</span></span>|  
|<span data-ttu-id="2db11-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2db11-499">PRIMARY_KEY</span></span>|<span data-ttu-id="2db11-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-500">Boolean</span></span>|  
|<span data-ttu-id="2db11-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2db11-501">UNIQUE</span></span>|<span data-ttu-id="2db11-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-502">Boolean</span></span>|  
|<span data-ttu-id="2db11-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2db11-503">CLUSTERED</span></span>|<span data-ttu-id="2db11-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-504">Boolean</span></span>|  
|<span data-ttu-id="2db11-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-505">TYPE</span></span>|<span data-ttu-id="2db11-506">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-506">Int32</span></span>|  
|<span data-ttu-id="2db11-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2db11-507">FILL_FACTOR</span></span>|<span data-ttu-id="2db11-508">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-508">Int32</span></span>|  
|<span data-ttu-id="2db11-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2db11-509">INITIAL_SIZE</span></span>|<span data-ttu-id="2db11-510">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-510">Int32</span></span>|  
|<span data-ttu-id="2db11-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="2db11-511">NULLS</span></span>|<span data-ttu-id="2db11-512">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-512">Int32</span></span>|  
|<span data-ttu-id="2db11-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2db11-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2db11-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-514">Boolean</span></span>|  
|<span data-ttu-id="2db11-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2db11-515">AUTO_UPDATE</span></span>|<span data-ttu-id="2db11-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-516">Boolean</span></span>|  
|<span data-ttu-id="2db11-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-517">NULL_COLLATION</span></span>|<span data-ttu-id="2db11-518">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-518">Int32</span></span>|  
|<span data-ttu-id="2db11-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-520">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-520">Int64</span></span>|  
|<span data-ttu-id="2db11-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-521">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-522">String</span><span class="sxs-lookup"><span data-stu-id="2db11-522">String</span></span>|  
|<span data-ttu-id="2db11-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-523">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-524">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-524">Guid</span></span>|  
|<span data-ttu-id="2db11-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-525">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-526">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-526">Int64</span></span>|  
|<span data-ttu-id="2db11-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-527">COLLATION</span></span>|<span data-ttu-id="2db11-528">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-528">Int16</span></span>|  
|<span data-ttu-id="2db11-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2db11-529">CARDINALITY</span></span>|<span data-ttu-id="2db11-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="2db11-530">Decimal</span></span>|  
|<span data-ttu-id="2db11-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="2db11-531">PAGES</span></span>|<span data-ttu-id="2db11-532">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-532">Int32</span></span>|  
|<span data-ttu-id="2db11-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2db11-533">FILTER_CONDITION</span></span>|<span data-ttu-id="2db11-534">String</span><span class="sxs-lookup"><span data-stu-id="2db11-534">String</span></span>|  
|<span data-ttu-id="2db11-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2db11-535">INTEGRATED</span></span>|<span data-ttu-id="2db11-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="2db11-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="2db11-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="2db11-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="2db11-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="2db11-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="2db11-539">Tables</span></span>  
  
-   <span data-ttu-id="2db11-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2db11-540">Columns</span></span>  
  
-   <span data-ttu-id="2db11-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2db11-541">Procedures</span></span>  
  
-   <span data-ttu-id="2db11-542">Представления</span><span class="sxs-lookup"><span data-stu-id="2db11-542">Views</span></span>  
  
-   <span data-ttu-id="2db11-543">Индексы</span><span class="sxs-lookup"><span data-stu-id="2db11-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2db11-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="2db11-544">Tables</span></span>  
  
|<span data-ttu-id="2db11-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-545">ColumnName</span></span>|<span data-ttu-id="2db11-546">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-547">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-548">String</span><span class="sxs-lookup"><span data-stu-id="2db11-548">String</span></span>|  
|<span data-ttu-id="2db11-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-550">String</span><span class="sxs-lookup"><span data-stu-id="2db11-550">String</span></span>|  
|<span data-ttu-id="2db11-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-551">TABLE_NAME</span></span>|<span data-ttu-id="2db11-552">String</span><span class="sxs-lookup"><span data-stu-id="2db11-552">String</span></span>|  
|<span data-ttu-id="2db11-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-553">TABLE_TYPE</span></span>|<span data-ttu-id="2db11-554">String</span><span class="sxs-lookup"><span data-stu-id="2db11-554">String</span></span>|  
|<span data-ttu-id="2db11-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-555">TABLE_GUID</span></span>|<span data-ttu-id="2db11-556">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-556">Guid</span></span>|  
|<span data-ttu-id="2db11-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-557">DESCRIPTION</span></span>|<span data-ttu-id="2db11-558">String</span><span class="sxs-lookup"><span data-stu-id="2db11-558">String</span></span>|  
|<span data-ttu-id="2db11-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-559">TABLE_PROPID</span></span>|<span data-ttu-id="2db11-560">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-560">Int64</span></span>|  
|<span data-ttu-id="2db11-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-561">DATE_CREATED</span></span>|<span data-ttu-id="2db11-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-562">DateTime</span></span>|  
|<span data-ttu-id="2db11-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-563">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2db11-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2db11-565">Columns</span></span>  
  
|<span data-ttu-id="2db11-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-566">ColumnName</span></span>|<span data-ttu-id="2db11-567">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-568">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-569">String</span><span class="sxs-lookup"><span data-stu-id="2db11-569">String</span></span>|  
|<span data-ttu-id="2db11-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-571">String</span><span class="sxs-lookup"><span data-stu-id="2db11-571">String</span></span>|  
|<span data-ttu-id="2db11-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-572">TABLE_NAME</span></span>|<span data-ttu-id="2db11-573">String</span><span class="sxs-lookup"><span data-stu-id="2db11-573">String</span></span>|  
|<span data-ttu-id="2db11-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-574">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-575">String</span><span class="sxs-lookup"><span data-stu-id="2db11-575">String</span></span>|  
|<span data-ttu-id="2db11-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-576">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-577">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-577">Guid</span></span>|  
|<span data-ttu-id="2db11-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-578">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-579">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-579">Int64</span></span>|  
|<span data-ttu-id="2db11-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-581">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-581">Int64</span></span>|  
|<span data-ttu-id="2db11-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2db11-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-583">Boolean</span></span>|  
|<span data-ttu-id="2db11-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2db11-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2db11-585">String</span><span class="sxs-lookup"><span data-stu-id="2db11-585">String</span></span>|  
|<span data-ttu-id="2db11-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2db11-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="2db11-587">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-587">Int64</span></span>|  
|<span data-ttu-id="2db11-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-588">IS_NULLABLE</span></span>|<span data-ttu-id="2db11-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-589">Boolean</span></span>|  
|<span data-ttu-id="2db11-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-590">DATA_TYPE</span></span>|<span data-ttu-id="2db11-591">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-591">Int32</span></span>|  
|<span data-ttu-id="2db11-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-592">TYPE_GUID</span></span>|<span data-ttu-id="2db11-593">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-593">Guid</span></span>|  
|<span data-ttu-id="2db11-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2db11-595">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-595">Int64</span></span>|  
|<span data-ttu-id="2db11-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2db11-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2db11-597">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-597">Int64</span></span>|  
|<span data-ttu-id="2db11-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2db11-599">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-599">Int32</span></span>|  
|<span data-ttu-id="2db11-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2db11-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="2db11-601">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-601">Int16</span></span>|  
|<span data-ttu-id="2db11-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2db11-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="2db11-603">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-603">Int64</span></span>|  
|<span data-ttu-id="2db11-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2db11-605">String</span><span class="sxs-lookup"><span data-stu-id="2db11-605">String</span></span>|  
|<span data-ttu-id="2db11-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2db11-607">String</span><span class="sxs-lookup"><span data-stu-id="2db11-607">String</span></span>|  
|<span data-ttu-id="2db11-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2db11-609">String</span><span class="sxs-lookup"><span data-stu-id="2db11-609">String</span></span>|  
|<span data-ttu-id="2db11-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="2db11-611">String</span><span class="sxs-lookup"><span data-stu-id="2db11-611">String</span></span>|  
|<span data-ttu-id="2db11-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2db11-613">String</span><span class="sxs-lookup"><span data-stu-id="2db11-613">String</span></span>|  
|<span data-ttu-id="2db11-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-614">COLLATION_NAME</span></span>|<span data-ttu-id="2db11-615">String</span><span class="sxs-lookup"><span data-stu-id="2db11-615">String</span></span>|  
|<span data-ttu-id="2db11-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2db11-617">String</span><span class="sxs-lookup"><span data-stu-id="2db11-617">String</span></span>|  
|<span data-ttu-id="2db11-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2db11-619">String</span><span class="sxs-lookup"><span data-stu-id="2db11-619">String</span></span>|  
|<span data-ttu-id="2db11-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-620">DOMAIN_NAME</span></span>|<span data-ttu-id="2db11-621">String</span><span class="sxs-lookup"><span data-stu-id="2db11-621">String</span></span>|  
|<span data-ttu-id="2db11-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-622">DESCRIPTION</span></span>|<span data-ttu-id="2db11-623">String</span><span class="sxs-lookup"><span data-stu-id="2db11-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2db11-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2db11-624">Procedures</span></span>  
  
|<span data-ttu-id="2db11-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-625">ColumnName</span></span>|<span data-ttu-id="2db11-626">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2db11-628">String</span><span class="sxs-lookup"><span data-stu-id="2db11-628">String</span></span>|  
|<span data-ttu-id="2db11-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2db11-630">String</span><span class="sxs-lookup"><span data-stu-id="2db11-630">String</span></span>|  
|<span data-ttu-id="2db11-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="2db11-632">String</span><span class="sxs-lookup"><span data-stu-id="2db11-632">String</span></span>|  
|<span data-ttu-id="2db11-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2db11-634">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-634">Int16</span></span>|  
|<span data-ttu-id="2db11-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2db11-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2db11-636">String</span><span class="sxs-lookup"><span data-stu-id="2db11-636">String</span></span>|  
|<span data-ttu-id="2db11-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-637">DESCRIPTION</span></span>|<span data-ttu-id="2db11-638">String</span><span class="sxs-lookup"><span data-stu-id="2db11-638">String</span></span>|  
|<span data-ttu-id="2db11-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-639">DATE_CREATED</span></span>|<span data-ttu-id="2db11-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-640">DateTime</span></span>|  
|<span data-ttu-id="2db11-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-641">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2db11-643">Представления</span><span class="sxs-lookup"><span data-stu-id="2db11-643">Views</span></span>  
  
|<span data-ttu-id="2db11-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-644">ColumnName</span></span>|<span data-ttu-id="2db11-645">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-646">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-647">String</span><span class="sxs-lookup"><span data-stu-id="2db11-647">String</span></span>|  
|<span data-ttu-id="2db11-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-649">String</span><span class="sxs-lookup"><span data-stu-id="2db11-649">String</span></span>|  
|<span data-ttu-id="2db11-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-650">TABLE_NAME</span></span>|<span data-ttu-id="2db11-651">String</span><span class="sxs-lookup"><span data-stu-id="2db11-651">String</span></span>|  
|<span data-ttu-id="2db11-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2db11-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="2db11-653">String</span><span class="sxs-lookup"><span data-stu-id="2db11-653">String</span></span>|  
|<span data-ttu-id="2db11-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-654">CHECK_OPTION</span></span>|<span data-ttu-id="2db11-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-655">Boolean</span></span>|  
|<span data-ttu-id="2db11-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2db11-656">IS_UPDATABLE</span></span>|<span data-ttu-id="2db11-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-657">Boolean</span></span>|  
|<span data-ttu-id="2db11-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2db11-658">DESCRIPTION</span></span>|<span data-ttu-id="2db11-659">String</span><span class="sxs-lookup"><span data-stu-id="2db11-659">String</span></span>|  
|<span data-ttu-id="2db11-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2db11-660">DATE_CREATED</span></span>|<span data-ttu-id="2db11-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-661">DateTime</span></span>|  
|<span data-ttu-id="2db11-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2db11-662">DATE_MODIFIED</span></span>|<span data-ttu-id="2db11-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="2db11-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2db11-664">Индексы</span><span class="sxs-lookup"><span data-stu-id="2db11-664">Indexes</span></span>  
  
|<span data-ttu-id="2db11-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="2db11-665">ColumnName</span></span>|<span data-ttu-id="2db11-666">DataType</span><span class="sxs-lookup"><span data-stu-id="2db11-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2db11-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-667">TABLE_CATALOG</span></span>|<span data-ttu-id="2db11-668">String</span><span class="sxs-lookup"><span data-stu-id="2db11-668">String</span></span>|  
|<span data-ttu-id="2db11-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="2db11-670">String</span><span class="sxs-lookup"><span data-stu-id="2db11-670">String</span></span>|  
|<span data-ttu-id="2db11-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-671">TABLE_NAME</span></span>|<span data-ttu-id="2db11-672">String</span><span class="sxs-lookup"><span data-stu-id="2db11-672">String</span></span>|  
|<span data-ttu-id="2db11-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2db11-673">INDEX_CATALOG</span></span>|<span data-ttu-id="2db11-674">String</span><span class="sxs-lookup"><span data-stu-id="2db11-674">String</span></span>|  
|<span data-ttu-id="2db11-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2db11-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="2db11-676">String</span><span class="sxs-lookup"><span data-stu-id="2db11-676">String</span></span>|  
|<span data-ttu-id="2db11-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-677">INDEX_NAME</span></span>|<span data-ttu-id="2db11-678">String</span><span class="sxs-lookup"><span data-stu-id="2db11-678">String</span></span>|  
|<span data-ttu-id="2db11-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2db11-679">PRIMARY_KEY</span></span>|<span data-ttu-id="2db11-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-680">Boolean</span></span>|  
|<span data-ttu-id="2db11-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2db11-681">UNIQUE</span></span>|<span data-ttu-id="2db11-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-682">Boolean</span></span>|  
|<span data-ttu-id="2db11-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2db11-683">CLUSTERED</span></span>|<span data-ttu-id="2db11-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-684">Boolean</span></span>|  
|<span data-ttu-id="2db11-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="2db11-685">TYPE</span></span>|<span data-ttu-id="2db11-686">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-686">Int32</span></span>|  
|<span data-ttu-id="2db11-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2db11-687">FILL_FACTOR</span></span>|<span data-ttu-id="2db11-688">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-688">Int32</span></span>|  
|<span data-ttu-id="2db11-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2db11-689">INITIAL_SIZE</span></span>|<span data-ttu-id="2db11-690">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-690">Int32</span></span>|  
|<span data-ttu-id="2db11-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="2db11-691">NULLS</span></span>|<span data-ttu-id="2db11-692">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-692">Int32</span></span>|  
|<span data-ttu-id="2db11-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2db11-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2db11-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-694">Boolean</span></span>|  
|<span data-ttu-id="2db11-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2db11-695">AUTO_UPDATE</span></span>|<span data-ttu-id="2db11-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-696">Boolean</span></span>|  
|<span data-ttu-id="2db11-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-697">NULL_COLLATION</span></span>|<span data-ttu-id="2db11-698">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-698">Int32</span></span>|  
|<span data-ttu-id="2db11-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2db11-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="2db11-700">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-700">Int64</span></span>|  
|<span data-ttu-id="2db11-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2db11-701">COLUMN_NAME</span></span>|<span data-ttu-id="2db11-702">String</span><span class="sxs-lookup"><span data-stu-id="2db11-702">String</span></span>|  
|<span data-ttu-id="2db11-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2db11-703">COLUMN_GUID</span></span>|<span data-ttu-id="2db11-704">Guid</span><span class="sxs-lookup"><span data-stu-id="2db11-704">Guid</span></span>|  
|<span data-ttu-id="2db11-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2db11-705">COLUMN_PROPID</span></span>|<span data-ttu-id="2db11-706">Int64</span><span class="sxs-lookup"><span data-stu-id="2db11-706">Int64</span></span>|  
|<span data-ttu-id="2db11-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2db11-707">COLLATION</span></span>|<span data-ttu-id="2db11-708">Int16</span><span class="sxs-lookup"><span data-stu-id="2db11-708">Int16</span></span>|  
|<span data-ttu-id="2db11-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2db11-709">CARDINALITY</span></span>|<span data-ttu-id="2db11-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="2db11-710">Decimal</span></span>|  
|<span data-ttu-id="2db11-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="2db11-711">PAGES</span></span>|<span data-ttu-id="2db11-712">Int32</span><span class="sxs-lookup"><span data-stu-id="2db11-712">Int32</span></span>|  
|<span data-ttu-id="2db11-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2db11-713">FILTER_CONDITION</span></span>|<span data-ttu-id="2db11-714">String</span><span class="sxs-lookup"><span data-stu-id="2db11-714">String</span></span>|  
|<span data-ttu-id="2db11-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2db11-715">INTEGRATED</span></span>|<span data-ttu-id="2db11-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="2db11-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2db11-717">См. также</span><span class="sxs-lookup"><span data-stu-id="2db11-717">See also</span></span>

- [<span data-ttu-id="2db11-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2db11-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
