# Database Functions

### insert\_user(name,password,username,role,email)

Takes name, password, username, role and email of the user as input and insert the user into the collection "users" in the database "nebula". If there is any problem inserting the user, the logger will display an error message. The function returns the ObjectId of the inserted document.

### create\_auth\_token(username,password)

Takes username and password as input and generate a unique authorization token for the user. It updates the auth token in the database. If there is any problem in updating the token then the logger will display an error message. It returns the generated token.

### check\_if\_exists(collection,field,value,field2=None,value2=None)

Takes collection, field, value, field2, value2 as input and checks whether a particular document is present in the collection or not by filtering the fields with their given values. Returns True if it finds any document otherwise returns False.

### fetch\_item(collection,field=None,value=None)

Takes collection, field and value as input and finds a particular document by filtering the field with the value. It returns the list of fetched documents.

### fetch\_item\_with\_projection(collection,projection,field=None,value=None)

Takes collection, projection, field and value as input and search a particular document in the collection by filtering the field with the value and returns the document with only those fields specified in the projection.

### authenticate\_user(token)

Takes authentication token as input and verify it from the database and if verified returns username otherwise returns none.

### insert\_dataset(datasetname,username):

Takes username and name of the dataset to be inserted as input and enters the details of it in the collection "datasets". If insertion fails, the logger will generate an error and returns none. The function returns the object id of the newly created document.

### update\_dataset(id,field,value)

Takes object id of a dataset, field and value as input and updates the field of the dataset by the given value. If the update fails, the logger will generate an error and returns false. On successful update, the function returns True.

### count\_images\_in\_db(dataset\_id)

Takes dataset id as input and counts the total number of images (or documents) in the collection "images" by filtering them with the dataset id. The function returns the total number of images found.

### count\_images\_in\_annotation(atype,annotation\_id)

Takes atype (annotation type) and annotation id as input and counts the total number of documents (images) in the collection "atype" by filtering them with the annotatiion\_id. The function returns the total count of the documents (images) found.

### insert\_image(filename,dataset\_id,imageurl,filesize,imageheight,imagewidth,imagehash,imageocr,imageicon,filetype,creator)

Takes different sets of parameters as input creates an entry in the collection "images" for all these fields. All these fields specify the details of an image. If the insertion fails, the logger will generate an error and returns none. After the successful insertion, it returns the inserted\_id.

### update\_image(imageid,field,value)

Takes image id, field and value as input and updates the field of the image, with the same image id,  by the given value. If the update fails, the logger will generate an error and returns false. After the successful update, it returns true.

### delete\_image\_by\_name(filename,datasetid)

Takes filename (image) and dataset id (in which the image is stored) as input and delete an image from the collection "images" which matches with the input filter values. It returns true after successful deletion otherwise returns false with logger displaying an error message.

### delete\_annotation\_by\_id(annotationid)

Takes annotation id as input and delete the document (annotation) from the collection "annotations" whose object id matches with the input annotation id. For successful deletion it returns true otherwise returns false with logger displaying an error message.

### delete\_many\_annotation\_entries(coll,annotationid)

Takes a collection name and annotation id as input and deletes all the annotations (document) from the input collection whose annotation id (object id) matches with the input id. For successful deletion it returns true otherwise returns false with logger displaying an error message.

### delete\_entry\_using\_annotationid\_and\_imageid(coll,annotationid,imageid)

Takes a collection name, annotation id and image id as input and deletes an entry (document) from the input collection by filtering it with the input annotation id and image id. For successful deletion it returns true otherwise returns false with logger displaying an error message.

### remove\_classname\_from\_segmentation(annotation\_id,className)

Takes annotation id and class name as input and removes the class name from all the documents of the collection "segmentation" whose annotation id matches with the input annotation id. It returns the total number of modified documents and in case of any error, the logger will display an error and the function returns none.

### insert\_annotation\_task(annotationname,annotationtype,annotationdescription,datasetnames,classnames,creator)

Takes all these input parameter values and creates an entry of these in the collection "annotations" and returns the inserted id and in case of any error, the logger will display an error and the function returns none.

### insert\_classification(annotationid,imageid,classname,state)

Takes all these input parameters and creates an entry from these in the collection "singlelabelimageclassification" for the classification task. It returns the inserted id and in case of any error, the logger will display an error and the function returns none.

### insert\_segmentation(annotationid,imageid,region,state)

Takes all these input parameters and creates an entry from these in the collection "segmentation" for the segmentation task. It returns the inserted id and in case of any error, the logger will display an error and the function returns none.

### insert\_extraction(annotationid,imageid,textregions,state)

Takes all these input parameters and creates an entry from these in the collection "extraction" for the extraction task. It returns the inserted id and in case of any error, the logger will display an error and the function returns none.

### count\_in\_collection(collection,field1=None,value1=None,field2=None,value2=None)

This function counts the total number of documents in the input collection satisfying the matching condition of the values for the respective fields. It returns the count of the documents found.

### fetch\_annotation\_images(collection,annotationid,filterbyclass=None,filterbystate=None)

Takes all these parameters as input and finds the documents (image) in the input collection by filtering according to these parameters. It finds the documents by matching its annotation id with the input and matching filterbyclass and filterbystate with the classname and state respectively if they are not set as None. It returns the list of extracted documents.

### update\_classification\_annotation(collection,annotationid,imageid,classname,state)

Takes these set of parameters as input and updates the class name and state of the document in the input collection for classification whose annotation id and image id matches with the input ids. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### update\_segmentation\_annotation(collection,annotationid,imageid,regions,state)

Takes these set of parameters as input and updates the regions and state of the document in the input collection for segmentation whose annotation id and image id matches with the input ids. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### get\_annotation\_value(collection,annotationid,imageid)

It finds the documents in the input collection by matching them with the annotation id and image id. Returns the list of extracted documents.

### update\_collection(collection,s1,v1,s2=None,v2=None,field=None,value=None)

Takes different sets of inputs and then selects the documents from the collection by matching the values specified by v1 and v2 for the fields s1 and s2 respectively and then update them by the given value (in the parameter value) in the given field (parameter field). It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### delete\_image\_from\_annotation(collection,annotation\_id,imageid)

Takes collection name, annotation id and image id as input and delete the document (image) from the collection whose annotation id and image id matches with the input ids. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### insert\_classification\_training(name,trainannotationid,testannotationid,description,imagesize,learningrate,epochs,modeltype,modelsize,batchsize,traintransforms,creator,optimizer)

Takes all these parameters as input and makes an entry of a new document, for the classification task, with all these fields in the collection "trainings". It returns inserted id for successful insertion and in case of any error, the logger will generate an error message and the function returns none.

### update\_classification\_training(trainingid,field,value)

It updates the given field by a given value, for classification, of a document in the collection "trainings" whose object id matches with the input trainingid. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### insert\_classification\_api(apiname,apidevice,apidescription,trainingid,filesize,webworkers,modelworkers,creator,port)

Takes all these parameters as input and makes an entry of a new document, for classification API, with all these fields in the collection "apis". It returns inserted id for successful insertion and in case of any error, the logger will generate an error message and the function returns none.

### update\_api(apiid,field,value)

It updates the given field by a given value of a document (api) in the collection "apis" whose object id match the input api id. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### delete\_api\_by\_id(apiid)

It deletes a document (api) from the collection "apis" whose object id match the input api id. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.

### insert\_ruleset(ruleSetName, username, ocrType, datasetId)

Takes all these parameters as input and makes an entry of a new document, for ruleset, with all these fields in the collection "rules". It returns inserted id for successful insertion and in case of any error, the logger will generate an error message and the function returns none.

### get\_dataset\_id(collection,rulesetid)

It finds a document in the input collection by matching the object id of documents with the input ruleset id and returns its datasetId. If it can't find any document then it returns none.

### update\_ruleset(rulesetid, field, value)

It updates the given field by a given value of a document (ruleset) in the collection "rules" whose object id match the input ruleset id. It returns True for a successful update and in case of any error, the logger will generate an error message and the function returns False.
