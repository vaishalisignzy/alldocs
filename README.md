# Onboarding Engine v1

Onboarding Engine is a RESTful APIs based solution that offers most of Signzy's APIs with simple requests. The onbaording engine includes all of Signzy's extraction and fetch solutions and a request to run the verification engine in all its glory. For the documentation of our verification engine, please refer this link: [http://docs.signzy.tech](http://docs.signzy.tech/)

### How to use this document <a href="#how-to-use-this-document" id="how-to-use-this-document"></a>

This document should be used as a reference for integrating the Signzy APIs and enabling the onboarding application. The section that is right side in the documentation contains the JSON requests and resposnes. The central column on this page will help you with detailed information about each endpoint.

### How the onboarding engine is the next version of verification engine. <a href="#how-the-onboarding-engine-is-the-next-version-of-verification-engine" id="how-the-onboarding-engine-is-the-next-version-of-verification-engine"></a>

The overall system and data inputs and outputs structure are as follows. Customer and merchant layer remain mostly the same as in the earlier integration (verification engine)

#### Customer Layer <a href="#customer-layer" id="customer-layer"></a>

1. This is the client account. This object is created by Signzy and contains the client’s username and password (API-key).
2. Multiple layers of administration & role creation are upcoming.

#### Merchant Layer <a href="#merchant-layer" id="merchant-layer"></a>

1. The merchant layer is created by the clients and requires the client credentials.
2. This layer is the end user layer and can be treated as a complete onboarding envelope.
3. Encapsulates an entire onboarding process through tags and documents corresponding to a particular tag.

#### Tag Layer <a href="#tag-layer" id="tag-layer"></a>

1. A tag is a data encapsulation object that
2. All data documents like PAN, aadhaar & other documents and fields like data for the person belong to a tag.
3. A tag can be extended to contain more data in the JSON parameters through documents.
4. Persona-based: For a particular onboarding, all the related data models like the company itself, its authorized signatories, beneficial owners etc can be created, giving more meaning to the integrating application

#### Document Layer <a href="#document-layer" id="document-layer"></a>

1. A tag can have multiple documents
2. The document may be any JSON structure and can be named, eg. Aadhaar, PAN
3. A document may be a simple JSON object that just stores data

The onboarding helps resolve the following limitations of an earlier version of ‘verification engine’:

1. A strongly coupled data structure
2. Limitation of types of documents that can be uploaded
3. Extendability and robustness
