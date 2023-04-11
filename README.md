# bloggers

## Question 1
1. Create a new project.
```
mix new blogger
```
2. Open the mix.exs file in your text editor and add httpoison to the list of dependencies:
```
defp deps do
  [
    {:httpoison, "~> 1.8"}
  ]
end
```
3. Run mix deps.get to install the dependencies.
Now, you can write the fetch_blog function in the Blogger module inside the `lib/blogger.ex` file
```
defmodule Blogger do
  use HTTPoison.Base

  def fetch_blog do
    url = "https://medium.com/podiihq/quick-connect-to-your-amazon-ec2-linux-instance-through-the-command-line-6c682960ef91"

    HTTPoison.get(url)
  end
end
```
4. Here, we're using the HTTPoison.get/1 function to fetch the blog post from the given URL. The use HTTPoison.Base line is required to use HTTPoison functions.

Now, you can test the function by running iex -S mix in your terminal and calling the function:
```
iex> Blogger.fetch_blog()
%HTTPoison.Response{
  body: "<!doctype html>...",
  headers: [
    {"Content-Type", "text/html"}, ...
  ],
  request: %HTTPoison.Request{
    body: "",
    headers: [],
    method: :get,
    options: [],
    params: %{},
    url: "https://medium.com/podiihq/quick-connect-to-your-amazon-ec2-linux-instance-through-the-command-line-6c682960ef91"
  },
  request_url: "https://medium.com/podiihq/quick-connect-to-your-amazon-ec2-linux-instance-through-the-command-line-6c682960ef91",
  status_code: 200
}
```
This should now return an HTTPoison response containing the blog post.

## Question 2
```
// Initial array.
var animals = ['cow', 'goat', 'sheet'];

// New Array.
var newAnimals = [];

// Function to return uppercase, takes two param, old and new array.
function adjustAnimals(oldArray, newArray) {
    // Targeting each item in array
    for (const item of oldArray) {
        // carrier for adjusted items
       var newitem = item.toUpperCase();
       // Add new item to new array
       newArray.push(newitem)
    };
    // Return new array, end function
    return newArray;
 };
// Calling the function on our arrays
adjustAnimals(animals, newAnimals);
// Confirming operation done
console.log(newAnimals);
````
