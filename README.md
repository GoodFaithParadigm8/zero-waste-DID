# Zero Waste Decentralized Identifiers - DIDs


1. Use DIDs in a practical manner, eg. build a Cosmos based CRM - and implement a zero waste initiative for the Interchange Earth Program.

### Potential Platforms outside of a sovereign CRM Chain(most ideal)
  - IXO
  - CHEQD_IO

Possible interoperability and/or collaborations.

### Abstract

The Waste industry is in need of an overhaul.  There is an opportunity to radically change the way people, communities, organizations and cities approach waste mitigation.  

> Zero Waste is the conservation of all resources by means of responsible production, consumption, reuse, and recovery of products, packaging, and materials without burning and with no discharges to land, water, or air that threaten the environment or human health.

## 1. Method for tracking waste stream and liable parties
 
We have identified a need to create a new standard based on Decentralized Identifiers <a name="myfootnote1">^1</a>: DIDs. The process which we see this method of waste mitigation being achieved is: 

1. Get Geoloacation from a portable device or electronic identifier from building area
	+ Loading Dock
	+ Kitchen
	+ Front Foyer
	+ Community/Neighborhood lat/log
	+ ect...  
2. Assign that location to the DID of person owning the recycle task
3. Assign that person to every identifier he/she belongs to
	+ Personal
	+ School
	+ Business
	+ Community
4. Conditional checks on location to give credit to business, residential community, place of worship or educational facility and/or individual person for reporting purposes


## 2. Example work flow code example

```javascript
Example: 
{
  "@context": "https://w3id.org/recycle/v1",
  "id": "did:recycle:123456789abcdefghi",
     // Array of keys associated with an individual
  "publicKey": [{
     // Personal Key
    "id": "did:example:123456789abcdefghi#keys-1",
    "type": "RsaVerificationKey2018",
    "controller": "did:example:123456789abcdefghi",
    "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n"
  }, { 	// Employer Key
    "id": "did:example:123456789abcdefghi#keys-3",
    "type": "Ieee2410VerificationKey2018",
    "controller": "did:example:123456789abcdefghi",
    "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n"
  },{  // Neighborhood/Community Key
    "id": "did:example:123456789abcdefghi#keys-3",
    "type": "Ieee2410VerificationKey2018",
    "controller": "did:example:123456789abcdefghi",
    "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n"
  }
  ],

  "authentication": [
      // this mechanism can be used to authenticate as did:...fghi
    "did:example:123456789abcdefghi#keys-1",
      // this mechanism can be used to biometrically authenticate as did:...fghi
    "did:example:123456789abcdefghi#keys-3",
	  // this mechanism is *only* authorized for authentication, it may not
	  // be used for any other proof purpose, so its full description is
	  // embedded here rather than using only a reference
    {
      "id": "did:example:123456789abcdefghi#keys-2",
      "type": "Ed25519VerificationKey2018",
      "controller": "did:example:123456789abcdefghi",
      "publicKeyBase58": "H3C2AVvLMv6gmMNam3uVAjZpfkcJCwDwnZn6z3wXmqPV"
    }
  ],

  "service": [{
      // Used broadcast transaction for city waste mitigation metric data 
    "id": "did:example:123456789abcdefghi#oidc",
    "type": "OpenIdConnectVersion1.0Service",
    "serviceEndpoint": "https://openid.example.com/recycle"
  }, {
    "id": "did:example:123456789abcdefghi#vcStore",
    "type": "CredentialRepositoryService",
    "serviceEndpoint": "https://repository.example.com/service/8377464"
  }, {
    "id": "did:example:123456789abcdefghi#xdi",
    "type": "XdiService",
    "serviceEndpoint": "https://xdi.example.com/8377464"
  }, {
    "id": "did:example:123456789abcdefghi#hub",
    "type": "HubService",
    "serviceEndpoint": "https://hub.example.com/.identity/did:example:0123456789abcdef/"
  }, {
    "id": "did:example:123456789abcdefghi#messaging",
    "type": "MessagingService",
    "serviceEndpoint": "https://example.com/messages/8377464"
  }, {
    "type": "RecycledGlassMaterial",
    "id": "did:example:123456789abcdefghi#business",
    "serviceEndpoint": "https://recycled.example.com/83hfh37dj",
    "description": "Waste diversion points",
    "recycledMaterial": {
      "weight": "12oz",
      "points" : "5",
      "currency": "USD"
    }
  }, {
    "type": "DidAuthPushModeVersion1",
    "id": "did:example:123456789abcdefghi#push",
    "serviceEndpoint": "http://auth.example.com/did:example:123456789abcdefghi"
  }, {
    "id": "did:example:123456789abcdefghi#bops",
    "type": "BopsService",
    "serviceEndpoint": "https://bops.example.com/enterprise/"
  }]
}
```

Authors
:  Jason Sprouse


### For an example of using JSON-GOLD

Clone:
`git clone https://github.com/piprate/json-gold.git`

Source file:
`cd examples`

Run the program:
`go run compact.go`

Import module here got errors that could not resolve, but as alluded - not sure if browser or Cosmos module would be best for JSON-LD.

## Footnotes

<sup>[1](#myfootnote1): Decentralized Identifiers (DIDs) are currently specified at v0.13 [w3c-Decentralized-Identifiers](https://w3c-ccg.github.io/did-spec/)</sup>
