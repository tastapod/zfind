# zfind - like find, but in jar/zip files

_Recursively search for files contained in jar/zip files._

This isn't for searching _inside_ the files, like zgrep, but
for matching the file names themselves. For instance:

    $ zfind org.apache.http.client.params.HttpClientParams ~/.m2

will search Maven's local cache for any jars containing the
HttpClientParams class. It turns out the dots in the package name
conveniently match slashes in the java class's name:

    /home/dnorth/.m2/repository/org/apache/httpcomponents/httpclient/4.0.1/httpclient-4.0.1.jar: org/apache/http/client/params/HttpClientParams.class

Ah, there it is!
