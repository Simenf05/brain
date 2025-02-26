2025-02-14 14:56

Status:
Tags: #communication #tcp #it #rdt #roundtriptime #udp

# Transport layer

The task of the transport layer is to provide a logical connection between different [[process|processes]]. The connection is used between different hosts meaning usually different machines or servers on the same network or over the internet. 

### House example
An analogy to this layer could be that if there was two houses with 12 children, then the host would be the house, the children would be the [[process|processes]] and letters sent between the houses would be transported by the transport layer. The transport layer has to know if a letter went missing on the way and resend lost letters.

### Transport layer protocols: TCP and UDP

The main two transport protocols is [[tcp|TCP]] and [[udp|UDP]]. They both divide the message to send up into ==segment==.
The difference between them is that TCP is connection-oriented and UDP is not. UDP does not require the processes to handshake and has no guarantee that it is reliable. TCP fixes this by implementing connection-oriented communication. With this it can guarantee that all segments will be sent and received. 

### [[Multiplexing and demultiplexing]]
The transport layer will break up the [[application layer|application layers]] message into parts called segments. This action is called [[multiplexing and demultiplexing|multiplexing]] and is one of the responsibilities of the transport layer. When splitting up the message it is easier to verify that the message is received properly, and the network requires packets to be smaller anyways. These segments is then passed to the [[networking layer]].

## [[Reliable data transfer]]

Reliable data transfer is the protocol that ensures that all data is delivered from end to end. The technology that is used today is the [[tcp|transport control protocol]], but we will not start on that protocol. On the page [[Reliable data transfer]] we will develop the protocol and at last we will arrive on the [[tcp]].






## References

- https://learn-eu-central-1-prod-fleet01-xythos.content.blackboardcdn.com/5def77a38a2f7/45357423?X-Blackboard-S3-Bucket=learn-eu-central-1-prod-fleet01-xythos&X-Blackboard-Expiration=1740333600000&X-Blackboard-Signature=veUW%2BCh3nOmdhH%2FQiLMmxI9IwgosC%2BaKFNADlCGZB08%3D&X-Blackboard-Client-Id=303508&X-Blackboard-S3-Region=eu-central-1&response-cache-control=private%2C%20max-age%3D21600&response-content-disposition=inline%3B%20filename%2A%3DUTF-8%27%271%2520-%2520Chapter_3_v8.01%2520-%2520Transport%2520layer%2520services%2520and%2520mux%2520demux%2520-%252023%2520slides%25281%2529.pdf&response-content-type=application%2Fpdf&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEN3%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaDGV1LWNlbnRyYWwtMSJHMEUCIQDBFtq5PNFozkxLM4B3GoCaG2F8SWaXEJdqyBTJCe9SpAIgCcW%2BK%2F2AQotHQw4WiD20bQzV3v71Efe0KJReQNnMAVcqvQUIFhAEGgw2MzU1Njc5MjQxODMiDMtsVntNzibnY%2BV9TyqaBbjiLaTasWQKGX5GvdgZLCnFC9%2B5s4XnAH44KlItzLl0r95YUNKkA1zYyO9M0TPIwObujGFgbOek%2FQ0Y%2Fvsv8hljOqdVJy%2BoHws2DzwXemyMQHVzUp9hV%2FsLSduT3wGDhE5j2DSU%2Fzvuke4%2BHiT35G5bTBe7zHIW5pXtvBtdI0OvxhhKuOqQQ0kFNWKYxdT1ctxoq4LzMLi1uR3r2plsZADSVivYiCCjZzzkmrusR58rglT%2FrhSObJAHrK7xJsEI0%2FyLWjjR8XlAhMBQOrnmhP3rFAcQg5J4kHfY2LR59FMPG5WTPupH1fVq0t8fXCCz5KIHEIdfeNg%2F8UfdF8xesHpDQlYCJpbyLMvXgBEtDa%2BPUMcGnTVMXYD5YE6LIyDjWdlyYi47Y%2FolMuSvPV3dxqAi2ybM%2B34S2EOlqn9%2B9Zr2hlpsc%2FhQaPj01%2B434PEwKOJ2f9wZPecivZAcgoz2Z1Wj%2BUxxBxGJgV%2B7FDhV%2FseYQ%2FzHa5f8PeP91IjtLuVtTgLIrE2AOUCUWUpcpjqXREIOHhwNYBUcC%2BQipNYd7Ofmk9P4UcB4Wjt6XSfkPWc6JaAmeEM2g5qsGe%2BEqRne2II7gvlraVgnVAEttJ%2Fo6sXlgRbgj3EBcd3RDdVvqdT51ms%2B1OHqnhQ5b4pYX63PaThSgbgk2ysRRy0KPMLv0AuShcOkv%2BUQC2U09jhAM0v97hhMKunwyWO3F9pvtoRc7ey1Z%2BFpXhmDU9USajS8five7gWkyka3sEu%2B1MO2hTuqOJIk73%2F2hHihGdsl6CLApbTcXvs6EXEKfeIeuXFbE61K7KB3y15l%2FGo7U2n%2BuNTDPOzKk3OSUXBdMCtNGVzY3LrOOb99v16Ft5ms7nJAqd6cigNbMzuPCx5GaDDzu%2By9BjqxAeR5ShJg%2F9hiNetjHKe2%2FoDjUeMJoEqX3wGab3lKnPpohOHoq8cVmQMNzuTSnyaCfOjYM73OxhlezkwnXJDp3wpIcH2TZOlw%2B7NPHfMzcvjMT3QS7iyFyEb7s2gnxlQnNqNqvKESVxxgw9mMn7yFy9HPJDHtEMojaRl16Umu1xWPUx5JC13Z8j2p0WjyBpZuwiSkZ9twz99jRHgw6Gd%2FB76ufXO9ttnrMh%2FrJDuOjEGnKA%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250223T120000Z&X-Amz-SignedHeaders=host&X-Amz-Expires=21600&X-Amz-Credential=ASIAZH6WM4PLSBJXVVTA%2F20250223%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Signature=0e585137c91c9da98a2fad1df02534b4fc628dafc039403b2b5e7d43d28908df 