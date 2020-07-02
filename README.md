Pikwy - Online Solution to create Screenshot <br>
<a style="color:white" href="https://pikwy.com/api.html">Documentation</a><br>

Python examples:<br>


    #!/usr/bin/python3
    import urllib.request
    import urllib.parse

    def generate_screenshot_api_url(token, options):
      api_url = 'https://api.pikwy.com/?token=' + token
      if token:
        api_url = api_url + '&url=' + options.get('url')
        api_url = api_url + '&width=' + options.get('width')
        api_url = api_url + '&height=' + options.get('height')
        api_url = api_url + '&response_type=' + options.get('response_type')
      return api_url;

    token = 'YOUR_API_TOKEN'
    options = {
      'url': 'https://www.wikipedia.org/',
      'width': '1280',
      'height': '2000',
      'response_type': 'image'
      }

    api_url = generate_screenshot_api_url(token, options)

    #save screenshot as an image
    opener = urllib.request.build_opener()
    urllib.request.install_opener(opener)
    output = 'output.png'
    urllib.request.urlretrieve(api_url, output)
