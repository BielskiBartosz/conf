package main

import (
	"encoding/json"
	"net/http"
)

type Message struct {
	Greeting string `json:"greeting"`
}

func main() {
	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		response := Message{Greeting: "Hello, World!"}
		w.Header().Set("Content-Type", "application/json")
		json.NewEncoder(w).Encode(response)
	})
	http.ListenAndServe(":8080", nil)
}
