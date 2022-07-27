# container

A container format is a file format that contains different parts.
The component parts of a container format may be called chunks, segments, streams, or something else.
In general, the component parts of a container format have some kind of header aand a body.
IFF is a chunk-based file format.
IFF chunks begin with a type ID, followed with a specifier of the length of the chunk.
RIFF and AIFF are file formats based on IFF, but TIFF (surprisingly) isn't 