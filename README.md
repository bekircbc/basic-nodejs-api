# Node server

      const server = http.createServer((req, res) => {
      const pathName = req.url;
      if (pathName === "/overview") {
      res.end("This is the OVERVIEW");
      } else if (pathName === "/product") {
      res.end("This is the PRODUCT");
      } else if (pathName === "/api") {
      res.end("API");
      } else {
      res.writeHead(404, {
      "Content-type": "text/html",
      "my-own-header": "hello-world",
      });
      res.end("<h1>Page not found!</h1>");
      }
      });
      server.listen(8000, () => {
      console.log("Listenning to requests on port 8000");
      });

# Callbcak Hell

      fs.readFile("txt/start.txt", "utf-8", (err, data1) => {

      fs.readFile(`txt/${data1}.txt`, "utf-8", (err, data2) => {
      fs.readFile("txt/append.txt", "utf-8", (err, data3) => {
      fs.writeFile("txt/final.txt", `${data2} ${data3}`, "utf-8", (err) => {
      if (err) throw err;
      console.log("Your file has been saved :D");
      });
      });
      });
      });
