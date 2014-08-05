Multipart
=========

An AngularJS module that helps build a multipart HTTP request body consisting of
binary and/or non-binary parts.

The resulting body can be returned either as an ArrayBuffer via req.getBuffer(),
or as a string via req.toString().

Usage:

    var req = new MultipartRequest('my_boundary');
    var part1 = new RequestPart();
    part1.addHeader('My-Header', 'some value');
    part1.addHeader('My-Other-Header', 'some other value');
    part1.setBody({ Title: "My Title" });
    req.addPart(part1);
    var part2 = new RequestPart();
    part2.addHeader('Content-Type', 'application/octet-stream');
    part2.setBody(<ARRAY_BUFFER>);
    req.addPart(part2);
    var buffer = req.getBuffer();
